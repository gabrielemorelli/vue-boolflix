<template>
  <div>
      <CardFilms v-for="(film, index) in films" :key="index" :film='film'/>
  </div>
</template>

<script>

import CardFilms from './partials/CardFilms.vue';
export default {
    name:"ListaFilms",
     props: {
        'films': Array
    },

    components: {
        CardFilms
    }
}
</script>

<style>

</style>