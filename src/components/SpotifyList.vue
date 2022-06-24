<template>
    <div class="vh-100 myBg">
        <div class="container pt-5">
            <div class="row">
                <div class="col-2" v-for="card in spotifyList" :key="card.year">
                    <SpotifyCard :info="card"></SpotifyCard>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import SpotifyCard from "./SpotifyCard.vue";

export default {
    components: { SpotifyCard },
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
</style>