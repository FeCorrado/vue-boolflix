<template>
  <div class="header-box">
    <div class="header-left">
      <h1>BOOLFLIX</h1>
    </div>
    <div class="header-right">
      <input type="text" placeholder="Cerca" v-model="keywordSearch" />
      <button @click="$emit('search', keywordSearch)">Cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      keywordSearch: "",
    };
  },
};
</script>

<style scoped lang="scss">
@import "../style/header.scss";
</style>
