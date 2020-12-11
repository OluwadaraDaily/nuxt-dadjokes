<template>
  <div class="container">
  	<div class="main">
  		<div class="text">
	  		<h1>Best Dad Jokes on the Continent</h1>
	  		<p>
	  			These jokes are premium jokes. <br> You do not want to miss out on these. <br> You can send to your <em>babe</em> or your <em>guys</em>.
	  		</p>
  		</div>

  		<img src="~/assets/img/img-01.jpg" height="400">

  	</div>

  	<div class="jokes-btn">
		<nuxt-link to="/jokes">
			<button>See Some Jokes</button>
		</nuxt-link>
	</div>

  </div>
</template>
<script>
export default {
	head () {
		return {
			title: "Dad Jokes"
		}
	}
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Russo+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');

html {
	padding: 0;
	margin: 0;
	background-color: #fff;
	font-family: 'Lato', sans-serif;
}
div .container {
	display: flex;
	justify-content: space-evenly;
	align-items: center;
	flex-flow: column wrap;
}
div .main {
	background-color: white;
	/*background-image: linear-gradient(to left, #3491d9, #fff);*/
	color: #3491d9;
}

div .main {
	width: 100%;
	height: 90vh;
}
.jokes-btn {
	margin: 0;

}

.jokes-btn a button {
	background-color: #3491d9;
	color: white;
	text-transform: uppercase;
	margin: 10px 0;
	padding: 8px;
	border: 1px solid #ccc;
	border-radius: 5px;
	width: 100%;
	cursor: pointer;
}

@media only screen and (min-width: 700px) {
	.container {
		margin: 30px auto auto 30%;
	}
}
</style>
