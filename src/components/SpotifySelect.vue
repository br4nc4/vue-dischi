<template>
    <div>
        <select @change="selectGenre" class="form-select" aria-label="Default select example">
            <option></option>
        </select>
    </div>
</template>

<script>
export default {
    props: {
        spotifylist: Array,
    },
    data(){
        return{
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