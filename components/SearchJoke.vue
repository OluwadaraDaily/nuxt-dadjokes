<template>
	<div>
		<form @submit.prevent="onSearch">
			<input type="text" v-model="text" name="search">
      <button><i class="fas fa-search"></i></button>
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
input, button {
  padding: 15px 10px;
  border-radius: 4px;
}

input[type="text"]{
  margin: 10px 0;
	width: 80%;
  font-size: 20px;
}

button {
  background-color: #3491d9;
  color: white;
  padding-top: 20px;
}

</style>
