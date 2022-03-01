<template>
 <main>
     <ListaFilms :films='films'/>
     <ListaSeries :series="series"/>
    
 </main>
</template>

<script>

import ListaFilms from './ListaFilms.vue'
import ListaSeries from './ListaSeries.vue'


export default {
    name: 'MyMain',
    props: {
        'films': Array,
        'series': Array,
    },
    components: {
        ListaFilms,
        ListaSeries
   
    }
}
</script>

<style>

</style>