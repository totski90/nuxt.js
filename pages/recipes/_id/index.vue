<template>	

	<section class="single-recipe">
		
		<h1>{{ recipe.title }}</h1>

		<div>
			<img class="recipe-image" :src="recipe.thumbnail" alt="recipe.title">

		</div>

		<p>{{ recipe.descriptionText }}</p>

	</section>

</template>

<script>

export default {	
	asyncData(context) {
			return new Promise((resolve, reject) => {
				setTimeout(() => {
					resolve({
						recipe: [
							{
								id: "1",
								title: "Delicious food",
								descriptionText: "This is really a description text",
								thumbnail: "https://upload.wikimedia.org/wikipedia/commons/6/64/Foods_%28cropped%29.jpg"
							},
							{
								id: "2",
								title: "What a nice place",
								descriptionText: "This is really a description text",
								thumbnail: "https://images.pexels.com/photos/556416/pexels-photo-556416.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
							}
						].find(el => el.id === context.params.id)				
					})
				}, 1500)
			})
		}
	}

</script>
<style scoped>
	
	.single-recipe {
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		padding: 30px;
		flex-flow: column;
	}

	.recipe-image {
		width: 100%;		
	}

</style>