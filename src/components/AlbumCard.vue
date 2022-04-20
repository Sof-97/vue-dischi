<template>
	<div class="text-white album-card d-flex flex-column align-items-center position-relative">
		<img class="mt-2" :src="image" :alt="author" />
        <h4 class="text-center mt-3">{{title}}</h4>
        <p class="position-absolute">
            <span>
                {{author}}
            </span>
            <br>
            <span>
                {{year}}
            </span>
        </p>
	</div>
</template>

<script>
export default {
	name: "AlbumCard",
	props: {
		image: String,
		author: String,
		title: String,
		year: String,
	},
};
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

.album-card {
    width: calc(100%/5 - 20px);
    padding: 10px;
    margin: 10px;
    background-color: $grey;
    padding-bottom: 80px;
	img {
		width: 80%;
		object-fit: cover;
	}
    p{
        text-align: center;
        opacity: 0.5;
        bottom: 0;
        font-weight: bolder;
    }
}
</style>
