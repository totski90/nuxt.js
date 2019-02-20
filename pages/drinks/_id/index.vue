<template>
	
	<section class="single-drink">
		<h1>{{ drinks.title }}</h1>

		<div>
			
			<img class="drink-image" :src="drinks.thumbnail" alt="drinks.title">

		</div>

		<p>{{ drinks.descriptionText }}</p>

	</section>

</template>

<script>
	export default {
		asyncData(context) {
			return new Promise((resolve, reject) => {
				setTimeout(() => {
					resolve({
						drinks: [
							{
								id: "1",
								title: 'Delicious Wine',
								descriptionText: "Awesome Drink",
								thumbnail: "https://media.gq.com/photos/598e11fbff5bc3695a1d3d07/3:2/w_800/game-of-throwns-wine-3x2.jpg"
							},
							{
								id: "2",
								title: 'Best Wine Ever',
								descriptionText: "Awesome Wine Ever...",
								thumbnail: "https://static.independent.co.uk/s3fs-public/thumbnails/image/2017/10/17/11/wine-cheese-food-istock-scorpp.jpg?width=1368&height=912&fit=bounds&format=pjpg&auto=webp&quality=70"
							},
							{
								id: "3",
								title: 'Another delicious wine',
								descriptionText: "delicious wine proven and tested",
								thumbnail: "https://www.chfi.com/wp-content/uploads/sites/2/2018/09/wine-and-cheese.jpg"
							},
							{
								id: "4",
								title: 'Try this amazing taste wine',
								descriptionText: "premium wine drink",
								thumbnail: "https://visitemporia.com/wp-content/uploads/2018/08/Wine-Cheese.jpg"
							}
						].find(el => el.id === context.params.id)
					})
				}, 1500)
			})
		}
	}
</script>

<style scoped>
	.single-drink {
		display: flex;
		justify-content: center;
		align-items: center;
		text-align: center;
		padding: 30px;
		flex-flow: column;
	}

	.drink-image {
		width: 100%;		
	}
</style>