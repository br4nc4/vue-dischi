<template>
    <div>
        <select onchange="selectGenre" class="form-select" aria-label="Default select example">
            <option></option>
        </select>
    </div>
</template>

<script>
export default {
    props: {
        spotifyList: Array,
    },
    data(){
        return{
            genreList: [],
        }
    },
    methods:{
        selectGenre(){
        },
        
    },
}
</script>

<style lang="scss" scoped>

</style>