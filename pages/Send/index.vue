<template>
  <div class="container">
  	<h1> Send a Random Joke To a Friend</h1> <hr>
  	<div id="form">
	  	<form @submit.prevent="sendJoke">
	  		<div>
	  			<label> Your Name </label> <br>
	  			<input type="text" v-model="name" name="s-name" required>
	  		</div>

	  		<div>
	  			<label> Receipient Email </label> <br>
	  			<input type="email" v-model="email" name="email" required>
	  		</div>

	  		<div>
	  			<label> Extra Message </label> <br>
	  			<textarea name="message" v-model="message" required></textarea>
	  		</div>

	  		<input type="submit" value="Send a Random Joke">
	  	</form>
	  </div> <hr>
	  <div>
	  	<p id="footer">Manage my dead UI abeg, no vex</p>
	  </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
	head() {
		return {
			title: "Send Joke"
		}
	},

	data() {
		return {
			email: "",
			name: "",
			message: "",
			joke: {}
		}
	},
	
	methods: {
		async sendJoke() {

			const config = {
				headers: {
					Accept: "application/json"
				}
			}
			const response_joke = await axios("https://icanhazdadjoke.com/", config)
			this.joke = response_joke.data
			// console.log(response.data)
			
			const body = {
				name: this.name,
				email: this.email,
				message: this.message,
				joke: this.joke
			}
			const response = await axios.post("http://127.0.0.1:3333/send", body)

			this.email = ""
			this.name = ""
			this.message = ""
			// console.log(body)
			console.log(response)
		}
	}
};
</script>

<style scoped>
	#form {
		margin: 0 auto;
		text-align: center;
	}
	input[type="text"], input[type="email"], textarea {
		width: 50%;
		padding: 10px 0;
		font-size: 20px;
		margin: 10px 0;
	}
	label {
		font-weight: bolder;
	}
	input[type="submit"] {
		padding: 8px;
		text-transform: uppercase;
	}
	#footer {
		color: #aaa;
	}
</style>
