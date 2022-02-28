<template>
  <div id="app">
    <MyHeader @search='getFilms' />
    <MyMain :films="films"/>
  </div>
</template>

<script>


import MyHeader from "./components/MyHeader.vue";
import MyMain from "./components/MyMain.vue";

const axios = require("axios");

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },

  data() {
    return {
      films: [],
    };
  },
  methods: {
    getfilms(keyword) {
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie/550?api_key=a26861d7ebab234184ab088f81a0bb79&query=" +
            keyword + '&language =it-IT'
        )

        .then((response) => {
          this.films = response.data.results;
        })

        .catch(function (error) {
          // handle error
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss">
</style>
