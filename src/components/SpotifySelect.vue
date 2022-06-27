<template>
    <div class="input-group">
        <select type="text" class="form-select" v-model="genre">
            <option value="">Scegli un genere</option>
            <option v-for="genere in listaGeneri" :key="genere" :value="genere">{{genere}}</option>
        </select>

        <button class="btn btn-secondary btn-outline" @click="onSearchClick">Cerca</button>
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
    methods: {
        onSearchClick(){
            this.$emit("searchGenre", this.genre);
        }
    },
}
</script>

<style lang="scss" scoped>

</style>