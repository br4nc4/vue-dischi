<template>
    <div class="input-group">
        <select type="text" class="form-select" v-model="genre">
            <option value="">Scegli un genere</option>
            <option v-for="genere in listaGeneri" :key="genere" :value="genere">{{genere}}</option>
        </select>

        <button class="btn btn-secondary btn-outline" @click="onSearchClick">Cerca</button>

        <select type="text" class="form-select ms-4" v-model="author">
            <option value="">Scegli un Artista</option>
            <option v-for="artista in listaArtisti" :key="artista" :value="artista">{{artista}}</option>
        </select>

        <button class="btn btn-secondary btn-outline" @click="onSearchArtist">Cerca</button>
    </div>
</template>

<script>
export default {
    props: {
        listaGeneri: Array,
        listaArtisti: Array,
    },
    data(){
        return{
            genre: "",
            author: "",
        }
    },
    methods: {
        onSearchClick(){
            this.$emit("searchGenre", this.genre);
        },
        onSearchArtist(){
            this.$emit("searchArtist", this.author);
        },
    },
}
</script>

<style lang="scss" scoped>

</style>