<template>
  <div>
  	<SearchJoke @search-text="onSearch"/>
  	<h1> All Jokes </h1>
    <Joke v-for="joke in jokes" :joke="joke.joke" :id="joke.id" :key="joke.id" />
  </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke'
import SearchJoke from '../../components/SearchJoke'
export default {
	component: {
		Joke,
		SearchJoke
	},
	head() {
		return {
			title: 'Random Jokes',
			meta: [{}]
		}
	},
	data () {
		return {
			jokes: []
		}
	},

	async created () {
		const config = {
			headers: {
				Accept: "application/json"
			}
		};
		const response = await axios.get('https://icanhazdadjoke.com/search', config)
		this.jokes = response.data.results;
	},
	methods: {
		async onSearch(text) {
			const config = {
				headers: {
					Accept: "application/json"
				}
			}
			const response = await axios.get("https://icanhazdadjoke.com/search?term=" + text, config)
			this.jokes = response.data.results
		}
	}
};
</script>

<style>
	body {
		color: #3491d9;
	}
</style>
