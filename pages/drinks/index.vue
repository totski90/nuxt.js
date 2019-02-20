<template>
	<section class="drinks">
		
		<Drink v-for="drink in drinks"
			:key="drink.id"
			:thumbnail="drink.thumbnail"
			:previewText="drink.previewText"
			:title="drink.title"
			:id="drink.id"
		/>

	</section>
</template>

<script>
	
	import Drink from '@/components/Drink';

	export default {
		components: {
			Drink
		},

		asyncData() {
			return new Promise((resolve, reject) => {
				setTimeout(() => {
					resolve({
						drinks: [
							{
								id: "1",
								title: 'Delicious Wine',
								previewText: "Awesome Drink",
								thumbnail: "https://media.gq.com/photos/598e11fbff5bc3695a1d3d07/3:2/w_800/game-of-throwns-wine-3x2.jpg"
							},
							{
								id: "2",
								title: 'Best Wine Ever',
								previewText: "Awesome Wine Ever...",
								thumbnail: "https://static.independent.co.uk/s3fs-public/thumbnails/image/2017/10/17/11/wine-cheese-food-istock-scorpp.jpg?width=1368&height=912&fit=bounds&format=pjpg&auto=webp&quality=70"
							},
							{
								id: "3",
								title: 'Another delicious wine',
								previewText: "delicious wine proven and tested",
								thumbnail: "https://www.chfi.com/wp-content/uploads/sites/2/2018/09/wine-and-cheese.jpg"
							},
							{
								id: "4",
								title: 'Try this amazing taste wine',
								previewText: "premium wine drink",
								thumbnail: "https://visitemporia.com/wp-content/uploads/2018/08/Wine-Cheese.jpg"
							}
						]
					})
				}, 1500)
			})
		}
	}

</script>

<style scoped>
	.drinks {
		display: flex;
		flex-flow: row wrap;
		justify-content: center;
		align-items: center;
	}

	a {
		text-decoration: none;
		color: black;
	}
</style>