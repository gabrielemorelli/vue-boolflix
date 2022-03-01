<template>
  <div id="app">
      <MyHeader @search="getFilms" />
    <MyMain :films="films" :series="series" />
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
    MyMain
  },

  data() {
    return {
      films: [],
      series: [],
      api_key:'a26861d7ebab234184ab088f81a0bb79',
      language:'it-IT'
    
    };
  },
  methods: {
    getFilms(keyword) {
      const params = {
     params:{
        'api_key': this.api_key,
        'query':keyword,
        'language':this.language
      }
      };
 
      
      axios
        .get(
          'https://api.themoviedb.org/3/search/movie/',params)

        .then((response) => {
          this.films = response.data.results;
        })

        .catch(function (error) {
          // handle error
          console.log(error);
        });
        
      axios
        .get(
          "https://api.themoviedb.org/3/search/tv/",params)

        .then((response) => {
          this.series = response.data.results;
         
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
