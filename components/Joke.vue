<template>
	<nuxt-link :to="'jokes/'+ id">
	  <div class="joke">
	  	{{ joke }}
	  </div>
	</nuxt-link>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke", "id"]
};
</script>

<style>
.joke {
	padding: 50px 0;
	margin: 10px 0;
	border: 2px solid black;
	transition: background-color 2s;
}
a{
	text-decoration: none;
	color: black;
}
a:hover .joke {
	background-color: black;
	color: white;
}
</style>
