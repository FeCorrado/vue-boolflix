<template>
  <div class="main-box">
    <Card
      v-for="(film, index) in films"
      :key="index"
      class="card"
      :immagine="film.backdrop_path"
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
    film: Array,
  },
};
</script>

<style scoped lang="scss">
@import "../style/mainBox.scss";
</style>
