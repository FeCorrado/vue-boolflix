<template>
  <div class="main-box">
    <Card
      v-for="(film, index) in filmArray"
      :key="index"
      class="card"
      :immagine="film.poster_path"
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
