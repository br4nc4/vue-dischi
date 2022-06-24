<template>
    <div class="vh-100 myBg">
        <div class="container ">
            <div class="row">
                <div class="col-5">

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    components: {},
    data() {
        return {
            apiURL: "https://flynn.boolean.careers/exercises/api/array/music",
            spotifyList: [],
        }
    },
    methods: {
        fetchSpotifyList() {
            axios.get(this.apiURL).then((resp) => {
                
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