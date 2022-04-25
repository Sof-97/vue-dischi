<template>
	<div id="app">
		<header>
			<HeaderComp @changeGenre="changeGenre" @changeArtist="changeArtist"/>
		</header>
		<main class="container">
			<AlbumsComp :selectedGenre="selectedGenre" :selectedArtist="selectedArtist"/>
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
			selectedGenre: '',
			selectedArtist: '',
		};
	},
	methods:{
		changeGenre(GenSel){
			this.selectedGenre = GenSel
		},
		changeArtist(ArtSel){
			this.selectedArtist = ArtSel
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
