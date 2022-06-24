<template>
    <div class="myCard h-100">
        <div>
            <img class="myImg" :src="info.poster" :alt="info.title">
        </div>

        <div class="text-center">
            <h5 class="text-white text-uppercase">{{info.title}}</h5>
            <p class="text-secondary">{{info.author}}</p>
            <p class="text-secondary">{{info.year}}</p>
        </div>
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
    }
</style>