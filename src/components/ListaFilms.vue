<template>
  <div>
    <h1>Lista Film</h1>
    <MyCard v-for="(film, index) in films" :key="index" :info="film" />
  </div>
</template>

<script>
import MyCard from "./partials/MyCard.vue";

export default {
  name: "ListaFilms",
  props: {
    'films': Array,
  },

  components: {
    MyCard
  }
};
</script>

<style>
</style>