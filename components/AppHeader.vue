<template>
  <header class="header">
  	<div class="nav-brand">
  		Dad Jokes
  	</div>

	<div class="ham">
	  	<i class="fa fa-bars fa-2x" @click="toggleBar"></i>
	</div>
  	
  	<div class="nav-links" id="nav-links">
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
	  	<div class="nav-link">
	  		<nuxt-link to="/send"> Send Joke </nuxt-link>
	  	</div>
	  </div>

  </header>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
  	return {
  		menuOpen: false
  	}
  },
  methods: {
  	toggleBar() {
  		
  		if(!this.menuOpen) {
  			const x = document.getElementById('nav-links');
  			x.classList.add('open')
  			this.menuOpen = true;
  		}
  		else {
  			const x = document.getElementById('nav-links');
  			x.classList.remove('open')
  			this.menuOpen = false;
  		}
  	}
  }
};
</script>

<style>
html {
	margin: 0;
	padding: 0;
}
.header {
	position: relative;
	padding:0;
	margin: 0;
	background-color: white;
	overflow: hidden;
	display: flex;
	flex-wrap: wrap;
	/*align-items: center;*/
	justify-content: space-between;
	color: #3491d9;
}
.nav-brand {
	font-size: 30px;
	font-weight: bolder;
}
.nav-link {
	display: block;
	margin: 5px 15px;
	
}
.nav-link a {
	text-transform: uppercase;
	padding: 5px;
	text-decoration: none;
	color: #3491d9;
	border-bottom: 1px solid #3491d9;
	/*border-radius: 6px;*/
}

.nav-link a:hover {
	background-color: white;
	color: #3491d9;
}


.ham {
	display: none;
}

@media only screen and (max-width: 667px) {
	.nav-brand {
		font-size: 30px;
		font-weight: bolder;
		width: 180px;
	}
	.nav-link {
		margin: 15px 0;
		
	}
	.nav-link a {
		border: none;
	}
	.nav-links {
		display: none;
	}
	.ham {
		display: block;
		cursor: pointer;
		text-align: right;
	}
	
	.header > div {
		width: 100%;
		flex: 0 50%;
	}
	.open {
		display: block;
	}
}

@media only screen and (min-width: 700px) {
	.nav-link {
		display: inline-block;
	}
}
</style>
