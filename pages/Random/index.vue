<template>
  <div class="container">
	<h1> Random Joke </h1>
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
		const config = {
			headers: {
				Accept: "application/json"
			}
		}
		const response = await axios("https://icanhazdadjoke.com/", config)
		this.joke = response.data
		console.log(response.data)
	}
};
</script>

<style scoped>
	
</style>
