<template>
  <div class="card">
    <div>
      <img :src="'https://image.tmdb.org/t/p/w500' + immagine" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    immagine: String,
  },
  data() {
    return {
      dischi: [],
      dischiFiltrati: [],
      generi: [],
      loading: true,
    };
  },
};
</script>

<style scoped lang="scss">
@import "../style/card.scss";
</style>
