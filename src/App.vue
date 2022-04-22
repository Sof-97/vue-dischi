<template>
	<div id="app">
		<header>
			<HeaderComp @changeGenre="changeGenre"/>
		</header>
		<main class="container">
			<AlbumsComp :selectedGenre="selected"/>
		</main>
	</div>
</template>

<script>
import "bootstrap";
import AlbumsComp from "./components/AlbumsComp.vue";
import HeaderComp from "./components/HeaderComp.vue";

export default {
	name: "App",
	components: {
		AlbumsComp,
		HeaderComp,
	},
	data() {
		return {
			selected: '',
		};
	},
	methods:{
		changeGenre(GenSel){
			this.selected = GenSel
		}
	}
};
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
@import "../src/style/variables.scss";
body {
	margin: 0;
	height: 100vh;
	background-color: $blue;
	div#app {
		height: 100vh;
		header {
			background-color: $grey;
			height: 6%;
			padding: 10px;
		}
		main {
			margin-top: 100px;
		}
	}
}
</style>
