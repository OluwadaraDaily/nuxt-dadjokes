<template>
	<div>
		<form @submit.prevent="onSearch">
			<input type="text" v-model="text" name="search">
			<input type="submit" value="Search">
		</form>
	</div>
</template>

<script>
export default {
  name: "SearchJoke",
  data () {
  	return {
  		text: ""	
  	}
  	
  },
  methods: {
  	onSearch() {
  		this.$emit('search-text', this.text)
  		this.text = "";
  	}
  }
  
};
</script>

<style scoped>
input {
	margin: 10px 0;
	padding: 8px 5px;
	border-radius: 4px;
}
input[type="text"]{
	width: 85%;
}

</style>
