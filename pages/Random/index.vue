<template>
  <div class="container">
  	<div class="top">
  		<h1> Random Joke </h1>
  		<button id="refresh" @click="refresh">Get another Random Joke</button>	
  	</div>
	
	<div class="joke">
		{{ joke.joke }}
	</div> <hr>

	<div class="joke-id">
		Joke ID: {{ joke.id }}
	</div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
	head() {
		return {
			title: "Random Joke"
		}
	},
	data () {
		return {
			joke: {}
		}
	},

	async created() {
		this.refresh()
	},
	methods: {
		async refresh() {
			const config = {
				headers: {
					Accept: "application/json"
			}
		}
			const response = await axios("https://icanhazdadjoke.com/", config)
			this.joke = response.data
			console.log(response.data)		
		}
	}
};
</script>

<style scoped>
	#refresh {
		padding: 5px;
	}
</style>
