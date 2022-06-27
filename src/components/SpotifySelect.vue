<template>
    <div>
        <select @change="selectGenre" class="form-select" aria-label="Default select example">
            <option v-for="genre in getGenre()" :key="genre">{{genre}}</option>
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
}
</script>

<style lang="scss" scoped>

</style>