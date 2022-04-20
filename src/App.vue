<template>
	<div id="app">
		<header>
			<img src="./assets/logo.svg" alt="" />
		</header>
		<main class="container">
			<AlbumsComp />
		</main>
	</div>
</template>

<script>
import "bootstrap";
import AlbumsComp from "./components/AlbumsComp.vue";

export default {
	name: "App",
	components: {
		AlbumsComp,
	},
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
			height: 5%;
			padding: 10px;
			img {
				height: 100%;
				margin-left: 6%;
			}
		}
		main {
			margin-top: 100px;
		}
	}
}
</style>
