<template>
  <div>
    <TheHeader :lista-generi="listaGeneri" @searchGenre="onSearchGenre"></TheHeader>

    <SpotifyList @genresUpdated="onGenresUpdate" :search-genre="searchGenre"></SpotifyList>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import SpotifyList from './components/SpotifyList.vue';




export default {
  components: {
    TheHeader,
    SpotifyList,
  },
  data() {
    return {
      listaGeneri: [],
      searchGenre: "",
    }
  },
  methods: {
    onGenresUpdate (listaGeneri) {
      console.log(listaGeneri);
      this.listaGeneri = listaGeneri
    },
    onSearchGenre(genre){
      this.searchGenre = genre;
    }
  },
}
</script>

<style lang="scss">

</style>
