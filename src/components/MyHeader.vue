<template>
  <header>
    <div class="title">BOOLFLIX</div>
    <div class="button">
      <input type="text" v-model="searchFilm">
      <button type="submit" @click="$emit('search',searchFilm)">Ricerca</button>
      
    </div>
  </header>
</template>

<script>
export default {
  name: "MyHeader",
  data() {
    return {
      searchFilm: ''
     
    };
  },
 
 
};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  justify-content: space-between;
  height: 100px;
  background-color: black;
  line-height: 100px;

  .title {
    color: red;
    margin-left: 20px;
  }

  .button {
    margin-right: 20px;
  }
}
</style>

