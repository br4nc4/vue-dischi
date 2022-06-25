<template>
    <div class="vh-100 myBg">
        <div class="container pt-5">
            <div>
                <SpotifySelect :spotifylist="spotifyList" @select="onSelectGenre"></SpotifySelect>
            </div>

            <div class="row row-cols-5 g-4">
                <div class="col" v-for="card in spotifyList" :key="card.title">
                    <SpotifyCard :info="card"></SpotifyCard>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import SpotifyCard from "./SpotifyCard.vue";
import SpotifySelect from "./SpotifySelect.vue";

export default {
    components: { SpotifyCard, SpotifySelect },
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            spotifyList: [],
        }
    },
    methods: {
        fetchSpotifyList() {
            axios.get(this.apiURL).then((resp) => {
                this.spotifyList = resp.data.response
            })
        },
        onSelectGenre(){
        },
        getGenre(){
            const list = [];
            this.spotifyList.forEach((disk) => {
                if(!list.includes(disk.genre)){
                    list.push(disk.genre)
                }
            });
            return list;
        }
    },
    mounted() {
        this.fetchSpotifyList()
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