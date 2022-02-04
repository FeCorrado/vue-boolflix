<template>
  <div id="app">
    <Header @search="filter" />
    <MainBox :filmArray="films" :tvArray="tv" />
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import MainBox from "./components/MainBox.vue";

export default {
  name: "App",
  components: {
    Header,
    MainBox,
  },
  data() {
    return {
      films: [],
      tv: [],
      cercare: "",
    };
  },
  mounted() {
    axios
      .get(
        `https://api.themoviedb.org/3/search/movie?query=tita&api_key=dba3d7b0f4b42d23bf86d3f1d4b9c93e`
      )
      .then((response) => {
        this.films = response.data.results;
        console.log(response.data.results);
      });
  },
  methods: {
    filter(keyword) {
      this.cercare = keyword;
      console.log(this.cercare);
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?query="${this.cercare}"&language=it-IT&api_key=dba3d7b0f4b42d23bf86d3f1d4b9c93e`
        )
        .then((response) => {
          this.films = response.data.results;
          console.log(response.data.results);
          console.log("s ", response.data.results[0]);
        });
      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?query="${this.cercare}"&language=it-IT&api_key=dba3d7b0f4b42d23bf86d3f1d4b9c93e`
        )
        .then((response) => {
          this.tv = response.data.results;
          console.log(response.data.results);
        });
    },
  },
};
</script>

<style lang="scss"></style>
