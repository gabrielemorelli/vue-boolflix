<template>
 <div>

    <h1>Lista Serie</h1>
    <ul>
      <li>
        <MyCard v-for="(serie, index) in series" :key="index" :info="serie" />
            
      </li>
    </ul>

   </div>
 
</template>


<script>

import MyCard from './partials/MyCard.vue';
export default {
  name: "ListaSeries",
  props: {
    'series': Array
  },
  components:{
    MyCard
  }
};

</script>

<style>

</style>