<template>
	<div>
		<img src="../assets/logo.svg" alt="" />
        <select class="form-select w-50" name="genre" id="genreSelect" v-model="selected"
        @change="$emit('changeGenre', selected)">
            <option disabled selected hidden>Scegli un genere</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="">Tutti i generi</option>
        </select>
	</div>
</template>

<script>
export default {
	name: "HeaderComp",
    data(){
        return{
            selected: ''
        }
    }
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
