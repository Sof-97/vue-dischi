<template>
    <div class="row justify-content-center">
        <AlbumCard :key="i" v-for="(item, i) in albumData"
        :image="item.poster"
        :author="item.author"
        :title="item.title"
        :year="item.year"/>
    </div>
</template>

<script>
import AlbumCard from "../components/AlbumCard.vue"
import axios from 'axios'
export default {
    name: "AlbumsComp",
    components:{
        AlbumCard,
    },
    data(){
        return{
            albumData: [],
        }
    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((res)=> {
            this.albumData = res.data.response;
        })
    }
}
</script>

