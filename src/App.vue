<template>
  <div>
    <TheHeader
    :lista-generi="listaGeneri" 
    @searchGenre="onSearchGenre"
    :lista-artisti="listaArtisti"
    @searchArtist="onSearchArtist"></TheHeader>

    <SpotifyList 
    @genresUpdated="onGenresUpdate" 
    :search-genre="searchGenre"
    @artistsUpdated="onArtistsUpdate"
    :search-artist="searchArtist"></SpotifyList>
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
      searchArtist: "",
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
    },
    onSearchArtist(author){
      this.searchArtist = author;
    },
  },
}
</script>

<style lang="scss">

</style>
