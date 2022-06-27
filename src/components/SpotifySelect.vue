<template>
    <div class="input-group">
        <select v-model="genre">
            <option>Scegli un genere</option>
            <option v-for="genere in listaGeneri" :key="genere" value="genere">{{genere}}</option>
        </select>

        <button @click="onSearchClick">Cerca</button>
    </div>
</template>

<script>
export default {
    props: {
        listaGeneri: Array,
    },
    data(){
        return{
            genre: ""
        }
    },
    methods:{
        onSearchClick(){
            this.$emit("searchGenre", this.genre);
        }
    },
}
</script>

<style lang="scss" scoped>

</style>