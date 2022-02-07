<template>
  <div class="card">
    <div class="block">
      <img
        v-if="immagine == null"
        :src="'https://image.tmdb.org/t/p/w500/A5EFlfWZA3yAiCvY7hwFLF0aV8I.jpg'"
        alt=""
      />
      <img v-else :src="'https://image.tmdb.org/t/p/w500' + immagine" alt="" />
    </div>
    <div class="none">
      <div><b>Titolo:</b> {{ titolo }}</div>
      <div><b>Titolo Originale:</b> {{ titoloorigine }}</div>
      <div class="conteiner-stelle">
        <div v-for="(voti, i) in stelle" :key="i" class="stelle">
          <i class="fas fa-star"></i>
        </div>
      </div>
      <div><b>Overview:</b> {{ desc }}</div>
      <div>
        <img
          v-if="lingua.includes(len)"
          class="flag"
          :src="len + '.png'"
          alt=""
        />
        <img v-else class="flag" :src="'nope.png'" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    immagine: String,
    titolo: String,
    titoloorigine: String,
    voti: Number,
    desc: String,
    len: String,
  },
  data() {
    return {
      lingua: ["it", "ja", "en", "fr", "ru"],
    };
  },
  computed: {
    stelle() {
      return Math.ceil(this.voti / 2);
    },
  },
};
</script>

<style scoped lang="scss">
@import "../style/card.scss";
</style>
