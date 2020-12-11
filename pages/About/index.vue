<template>
  <div>
  	<h1>About Dad Jokes</h1> <hr>
  	<p>
  		This is a web application that showcases some awful jokes utilising <a href="https://icanhazdadjoke.com/api"> Dad Jokes API </a> <br> <br>
  		It is awful but it is worth it (lmao) <br>
  		You can also check out the Github Repository of the <a href="https://github.com/OluwadaraDaily/nuxt-dadjokes">web</a> and <a href="https://github.com/OluwadaraDaily/dadjokes-api">API</a>.
  	</p>
  </div>
</template>

<script>
export default {
	head () {
		return {
			title: "About Dad Jokes"
		}
	}
};
</script>

<style scoped>
	a {
		text-decoration: underline;
	}
</style>


