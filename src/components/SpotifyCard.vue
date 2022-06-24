<template>
    <div class="cardBg text-center">
        <img class="myImg" :src="info.poster" :alt="info.title">
        <h5 class="text-white text-uppercase">{{info.title}}</h5>
        <div class="text-secondary">{{info.author}}</div>
        <div class="text-secondary">{{info.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'SpotifyCard',
    props: {
        info: Object,
    },
}
</script>

<style lang="scss" scoped>
    .cardBg{
        background-color: #2e3a46;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        height: 100%;
        width: 200px;
        padding: 1rem 1rem;
    }

    .myImg{
        aspect-ratio: 1/1;
        width: 140px;
    }
</style>