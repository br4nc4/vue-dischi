<template>
  <div>
    <TheHeader :lista-generi="listaGeneri" @searchGenre="onSearchGenre"></TheHeader>

    <SpotifyList 
    @genresUpdated="onGenresUpdate" 
    :search-genre="searchGenre"
    @artistsUpdated="onArtistsUpdate"></SpotifyList>
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
      listaArtisti: [],
      searchGenre: "",
    }
  },
  methods: {
    onGenresUpdate (listaGeneri) {
      console.log(listaGeneri);
      this.listaGeneri = listaGeneri;
    },
    onArtistsUpdate (listaArtisti){
      console.log(listaArtisti);
      this.listaArtisti = listaArtisti;
    },
    onSearchGenre(genre){
      this.searchGenre = genre;
    }
  },
}
</script>

<style lang="scss">

</style>
