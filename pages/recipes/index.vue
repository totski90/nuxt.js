<template>

	<section class="recipes">

		<Recipe	v-for="recipe in recipes"
			:key="recipe.id"
			:thumbnail="recipe.thumbnail"
			:title="recipe.title"
			:id="recipe.id"		
			:previewText="recipe.previewText"	
		/>

	</section>

</template>

<script>
	
	import Recipe from '@/components/Recipe';

	export default {
		components: {
			Recipe
		},

		asyncData() {
			return new Promise((resolve, reject) => {
				setTimeout(() => {
					resolve({
						recipes: [
							{
								id: "1",
								title: "Delicious food",
								previewText: "Awesome food desert!",
								thumbnail: "https://upload.wikimedia.org/wikipedia/commons/6/64/Foods_%28cropped%29.jpg"
							},
							{
								id: "2",
								title: "What a nice place",
								previewText: "A beutiful place to live in!",
								thumbnail: "https://images.pexels.com/photos/556416/pexels-photo-556416.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
							}
						]
					})
				}, 1500)
			})
		}
	}

</script>

<style scoped>

	.recipes    {
		display: flex;
		flex-flow: row wrap;
		justify-content: center;
		align-items: center;
	}

</style>