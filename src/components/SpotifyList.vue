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
        searchArtist: String,
    },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            spotifyList: [],
        }
    },
    computed: {
        filteredAlbums() {
            if(!this.searchGenre && !this.searchArtist){
                return this.spotifyList
            }
            else if (this.searchGenre) {
                return this.spotifyList.filter(album => {
                    return album.genre.includes(this.searchGenre)
                })
            }
            else if (this.searchArtist) {
                return this.spotifyList.filter(album => {
                    return album.author.includes(this.searchArtist)
                })
            }
            else {
                return this.spotifyList.filter(album => {
                    return album.genre.includes(this.searchGenre) && album.author.includes(this.searchArtist)
                })
            }
        },
    },
    methods: {
        fetchSpotifyList() {
            axios.get(this.apiURL).then((resp) => {
                this.spotifyList = resp.data.response

                this.$emit("genresUpdated", this.listaGeneri());

                this.$emit("artistsUpdated", this.listaArtisti());
            })
        },
        listaGeneri() {
            const lista = [];
            this.spotifyList.forEach((album) => {
                if(!lista.includes(album.genre)){
                    lista.push(album.genre);
                }
            })
            return lista;
        },
        listaArtisti() {
            const list = [];
            this.spotifyList.forEach((album) => {
                if(!list.includes(album.author)){
                    list.push(album.author);
                }
            })
            return list;
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