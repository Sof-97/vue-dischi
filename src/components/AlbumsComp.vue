<template>
	<div class="row justify-content-center">
		<AlbumCard
			:key="i"
			v-for="(item, i) in filter"
			:image="item.poster"
			:author="item.author"
			:title="item.title"
			:year="item.year"
		/>
		<h5 v-show="this.filter.length == 0 ">Nessun risultato trovato</h5>
	</div>
</template>

<script>
import AlbumCard from "../components/AlbumCard.vue";
import axios from "axios";
export default {
	name: "AlbumsComp",
	components: {
		AlbumCard,
	},
	data() {
		return {
			albumData: [],
			found: null,
		};
	},
	props: {
		selectedGenre: String,
		selectedArtist: String,
	},
	created() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then(res => {
				this.albumData = res.data.response;
				this.found = res.data.response.length;
			});
	},
	computed: {
		filter: function () {
			if (this.selectedGenre === "" && this.selectedArtist === "") {
				return this.albumData;
			} else if (this.selectedGenre != "" && this.selectedArtist === "") {
				return this.albumData.filter(e => {
					return e.genre == this.selectedGenre;
				});
			} else if (
				this.selectedGenre === "" &&
				this.selectedArtist !== ""
			) {
				return this.albumData.filter(e => {
					return e.author == this.selectedArtist;
				});
			} else {
				return this.albumData.filter(e => {
					return (
						e.author == this.selectedArtist &&
						e.genre == this.selectedGenre
					);
				});
			}
		},
	},
};
</script>

<style scoped>
h5{
	color: white;
	text-align: center;
}
</style>