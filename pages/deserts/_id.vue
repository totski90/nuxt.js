<template>
	
	<div class="container">
	
		<article>
			<h1 class="title">{{ desert.title }}</h1>
			<p>{{ desert.previewText }}</p>
		</article>
		<br>
		<hr>
		<hr>
		<aside>
			<h3>Desert you might enjoy</h3>
			<ul>
				<li v-for="related in relatedDeserts">
					<nuxt-link :to="{name: 'deserts-id', params: {id: related.id}}">
						{{ related.title }}
					</nuxt-link>
				</li>
			</ul>
		</aside>

	</div>

</template>

<script>

	export default {
		
		data() {
			return {
				id: this.$route.params.id
			}
		},
		computed: {
			desert() {
				return this.$store.state.deserts.all.find(desert => desert.id === this.id)
			},
			relatedDeserts() {
				return this.$store.state.deserts.all.filter(desert => desert.id !== this.id)
			}
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
	.container {	    
	    justify-content: space-between;
	    line-height: 1.5;
		display: flex;
		justify-content: center;		
		text-align: center;
	  }

</style>