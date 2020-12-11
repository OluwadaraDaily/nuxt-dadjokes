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
	padding: 50px 10px;
	margin: 30px 0;
	border: 1px solid #fff;
	border-radius: 20px;
	-webkit-box-shadow: 4px 4px 11px 0px rgba(52, 145, 217, 0.78);
	-moz-box-shadow:    4px 4px 11px 0px rgba(52, 145, 217, 0.78);
	box-shadow:         4px 4px 11px 0px rgba(52, 145, 217, 0.78);
	font-size: 22px;
}
a{
	text-decoration: none;
	color: black;
}

</style>
