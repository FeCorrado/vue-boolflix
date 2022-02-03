<template>
  <div class="">
    <div>
      <img :src="immagine" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    immagine: String,
  },
};
</script>

<style scoped lang="scss">
@import "../style/card.scss";
</style>
