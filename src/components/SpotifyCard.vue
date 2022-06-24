<template>
    <div>
        <div class="cardBg">
            <img class="myImg" :src="info.poster" :alt="info.title">
            <h5>{{info.title}}</h5>
            <div>{{info.author}}</div>
            <div>{{info.year}}</div>
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
    .cardBg{
        background-color: #2e3a46;
    }

    .myImg{
        aspect-ratio: 1/1;
        width: 140px;
    }
</style>