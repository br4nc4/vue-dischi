<template>
    <div class="myCard h-100">
        <div>
            <img class="myImg" :src="albumPoster" :alt="album.title" @error="onImgError"/>
        </div>

        <div class="text-center">
            <h5 class="text-white text-uppercase">{{album.title}}</h5>
            <p class="text-secondary mb-0 lh-1 fw-semibold">{{album.author}}</p>
            <p class="text-secondary lh-1 fw-semibold">{{album.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SpotifyCard',
    props: {
        album: Object,
    },
    data() {
        return {
            albumPoster: "",
        }
    },
    methods: {
        onImgError() {
            this.albumPoster = "/img/noimage.jpg";
        },
    },
    mounted() {
        this.albumPoster = this.album.poster;
    }
}
</script>

<style lang="scss" scoped>
    .myCard{
        background-color: #2e3a46;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 180px;
        padding: 1rem 1rem;
        cursor: pointer;
    }

    .myImg{
        aspect-ratio: 1/1;
        width: 100%;
        margin-bottom: 1.2rem;
    }

    h5{
        margin-bottom: 1rem;
    }
</style>