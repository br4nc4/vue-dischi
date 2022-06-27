<template>
  <div>
    <TheHeader :lista-generi="listaGeneri" @searchGenre="onSearchGenre($event)"></TheHeader>
    <SpotifyList @generesUpdated="onGeneresUpdated" :search-genre="searchGenre"></SpotifyList>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import SpotifyList from './components/SpotifyList.vue';




export default {
  data() {
    return {
      listaGeneri: [],
      searchGenre: "",
    }
  },
  components: {
    TheHeader,
    SpotifyList,
  },
  methods: {
    onGeneresUpdated (listaGeneri) {
      console.log(listaGeneri);
      this.listaGeneri = listaGeneri
    },
    onSearchGenre(genre){
      this.onSearchGenre = genre;
    }
  },
}
</script>

<style lang="scss">

</style>
