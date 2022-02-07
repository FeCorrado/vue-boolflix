<template>
  <div class="main-box">
    <div class="card-box">
      <h1>FILM</h1>
      <div class="cards">
        <Card
          v-for="(film, index) in filmArray"
          :key="index"
          class="card"
          :immagine="film.poster_path"
          :titolo="film.title"
          :titoloorigine="film.original_title"
          :voti="film.vote_average"
          :desc="film.overview"
          :len="film.original_language"
        />
      </div>
      <h1 class="serie">SERIE</h1>
      <div class="cards">
        <Card
          v-for="(tv, index) in tvArray"
          :key="index"
          class="cards"
          :immagine="tv.poster_path"
          :titolo="tv.name"
          :titoloorigine="tv.original_name"
          :voti="tv.vote_average"
          :desc="tv.overview"
          :len="tv.original_language"
        />
      </div>
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
