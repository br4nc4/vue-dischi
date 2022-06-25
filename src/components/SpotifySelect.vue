<template>
    <div>
        <select @change="selectGenre" class="form-select" aria-label="Default select example"
        v-model="value">
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    data(){
        return{
            value: ""
        }
    },
    methods:{
        selectGenre(){
            this.$emit("select", this.value)
        }
    }
}
</script>

<style>

</style>