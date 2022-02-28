<template>
 <main>
     <ListaFilms :films='films'/>
 </main>
</template>

<script>

import ListaFilms from './ListaFilms.vue'
export default {
    name: 'MyMain',
    props: {
        'films': Array
    },
    components: {
        ListaFilms
    }
}
</script>

<style>

</style>