<template>
  <div class="container">
  	<h1> Joke as an Image </h1>
  	<img :src="'https://icanhazdadjoke.com/j/' + $route.params.id + '.png'"> <hr>
  	<h1> Joke as a text </h1>
    <div class="joke">
    	{{ joke.joke }}
    </div> <hr> <br>

    <div class="id">
    	Joke ID: {{ joke.id }}
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
	head() {
		return {
			title: "Some joke",
			meta: [{}]
		}
	},

	data() {
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
		const response = await axios.get(`https://icanhazdadjoke.com/j/`+ this.$route.params.id, config)

		this.joke = response.data
	}
};
</script>

<style>

</style>
