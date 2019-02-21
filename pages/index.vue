<template>
  <section class="container">
  	<div>
  		<h1 class="title">Nuxt core features</h1>
  		<h2 class="subtitle">
  			My nuxt core features reference
  		</h2>

  		<div class="link">
  			<nuxt-link
  				v-for="link in links"
  				:to="{name: 'deserts-id', params: {id: link.id}}"
  				:key="link.id"
  				class="button--grey"
  			>
  				{{ link.title }}
  			</nuxt-link>
  		</div> 		

  		<div class="images">
			<Featured v-for="feature in features"
				:key="feature.id"
				:thumbnail="feature.thumbnail"
				:title="feature.title"
				:previewText="feature.previewText"
			/>
	  	</div>  		
  	</div>
  </section>

</template>

<script>
	import Featured from '@/components/Featured'	

	export default {
		components: {
			Featured
		},

		computed: {
			links() {
				return this.$store.state.deserts.all
			},

			features() {
				return this.$store.state.featured.all
			}
		}
	}

</script>

<style scoped>
	
	.title {
	  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
	  'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
	  display: block;
	  font-weight: 300;
	  font-size: 100px;
	  letter-spacing: 1px;
	}
	.subtitle {
	  font-weight: 300;
	  font-size: 42px;
	  color: #526488;
	  word-spacing: 5px;
	}
	.container {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  text-align: center;
	}
	.images {
		margin-top: 2px;
		margin-bottom: 2px;
		display: flex;
		flex-flow: row wrap;
		justify-content: center;
		align-items: center;
	}

	.link {
		padding: 5px 0 10px 0;
	}

</style>