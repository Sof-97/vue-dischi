<template>
	<div>
		<img src="../assets/logo.svg" alt="" />
		<select
			class="form-select w-25"
			name="genre"
			id="genreSelect"
			v-model="selectGenre"
			@change="$emit('changeGenre', selectGenre)"
		>
			<option disabled selected hidden>Scegli un genere</option>
			<option value="Rock">Rock</option>
			<option value="Pop">Pop</option>
			<option value="Jazz">Jazz</option>
			<option value="Metal">Metal</option>
			<option value="">Tutti i generi</option>
		</select>
		<select class="form-select w-25" name="artist" id="artistSelect" v-model="selectArtist" @change="$emit('changeArtist', selectArtist)">
			<option disabled selected hidden>Scegli un artista</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jackson</option>
			<option value="">Tutti gli artisti</option>
		</select>
	</div>
</template>

<script>
export default {
	name: "HeaderComp",
	data() {
		return {
			selectGenre: "",
			selectArtist: "",
		};
	},
};
</script>

<style lang="scss" scoped>
div {
	display: flex;
	justify-content: space-around;
	height: 100%;
	img {
		height: 100%;
	}
}
</style>
