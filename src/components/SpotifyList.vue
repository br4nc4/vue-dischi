<template>
    <div class="vh-100 myBg d-flex flex-column">
        <div class="container overflow-auto pt-5">
            <div class="row row-cols-5 g-4">
                <div class="col" v-for="album in filteredAlbums" :key="album.title">
                    <SpotifyCard :album="album"></SpotifyCard>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import SpotifyCard from "./SpotifyCard.vue";

export default {
    components: { SpotifyCard, },
    props: {
        searchGenre: String,
    },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            spotifyList: [],
        }
    },
    computed: {
        filteredAlbums() {
            if(!this.searchGenre){
                return this.spotifyList
            }
            return this.spotifyList.filter((album) => {
                return album.genre === this.searchGenre
            })
        }
    },
    methods: {
        fetchSpotifyList() {
            axios.get(this.apiURL).then((resp) => {
                this.spotifyList = resp.data.response

                this.$emit("generesUpdated", this.listaGeneri())
            })
        },
        listaGeneri() {
            const lista = [];
            this.spotifyList.forEach((album) => {
                if(!lista.includes(album.genre)){
                    lista.push(album.genre)
                }
            })
            return lista;
        },
    },
    mounted() {
        this.fetchSpotifyList();
    }
}
</script>

<style lang="scss" scoped>
    .myBg{
        background-color: #1e2d3b;
    }

    .container{
        max-width: 1070px;
    }
</style>