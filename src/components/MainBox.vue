<template>
  <div class="main-box">
    <div>
      <h1>FILM</h1>
    </div>
    <div class="cards">
      <Card
        v-for="(film, index) in filmArray"
        :key="index"
        class="card"
        :immagine="film.poster_path"
        :titolo="film.title"
        :titoloorigine="film.original_title"
        :voto="film.vote_average"
        :desc="film.overview"
      />
      <h1>Serie</h1>
    </div>
    <div class="cards">
      <Card
        v-for="(tv, index) in tvArray"
        :key="index"
        class="cards"
        :immagine="tv.poster_path"
        :titolo="tv.title"
        :titoloorigine="tv.original_title"
        :voto="tv.vote_average"
        :desc="tv.overview"
      />
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
export default {
  components: {
    Card,
  },
  props: {
    filmArray: Array,
    tvArray: Array,
  },
};
</script>

<style scoped lang="scss">
@import "../style/mainBox.scss";
</style>
