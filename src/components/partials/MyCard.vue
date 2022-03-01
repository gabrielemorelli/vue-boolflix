<template>
  <ul>
    <li>
      <div>{{getTitle()}}</div>
      <img :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`">    
      <div>
      <img v-if="languages.includes(info.original_language)" :src="require('../../assets/flag/'+ info.original_language +'.png')"> 
      <span v-else>{{ info.original_language}}</span>
      </div>
      
      
      <div>
      <i  v-for="i in 5" :key="i" class="fa-star" :class="(i < getStar()) ? 'fa-solid' :'fa-regular'"></i>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "MyCard",
  props: {
    info: Object,
  },
  data() {
    return {
      languages: ["en", "it"],
    };
  },
  methods: {
    getTitle() {
      if (this.info.title) {
        return this.info.title;
      } else {
        return this.info.name;
      }
    },
    getStar() {
      return Math.ceil(this.info.vote_average / 2);
    }
  }
};
</script>

<style >
</style>