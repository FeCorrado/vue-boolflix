<template>
  <div class="main-box">
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
  },
};
</script>

<style scoped lang="scss">
@import "../style/mainBox.scss";
</style>
