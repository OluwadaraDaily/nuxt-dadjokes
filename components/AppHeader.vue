<template>
  <header class="header">
  	<div class="nav-link nav-brand">
  		Dad Jokes
  	</div>
  	<div class="nav-links">
	  	<div class="nav-link">
	  		<nuxt-link to="/"> Home </nuxt-link>
	  	</div>
	  	<div class="nav-link">
	  		<nuxt-link to="/jokes"> Jokes </nuxt-link>
	  	</div>
	  	<div class="nav-link">
	  		<nuxt-link to="/about"> About </nuxt-link>
	  	</div>
	  	<div class="nav-link">
	  		<nuxt-link to="/random"> Random Joke </nuxt-link>
	  	</div>
	  </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader"
};
</script>

<style>
html {
	margin: 0;
	padding: 0;
}
.header {
	padding:0;
	margin: 0;
	background-color: #db9e9a;
	display: flex;
	align-items: center;
	justify-content: space-between;
}
.nav-brand {
	font-size: 30px;
	font-weight: bolder;
}
.nav-link {
	display: inline-block;
	margin: 5px 10px;
	
}
.nav-link a {
	text-transform: uppercase;
	padding: 5px;
	text-decoration: none;
	color: black;
	border: 1px solid black;
	border-radius: 6px;
}

.nav-link a:hover {
	background-color: #000;
	color: #db9e9a;
}
</style>
