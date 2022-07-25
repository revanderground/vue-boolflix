<template>
  <main>
      <h2 v-if="series.length===0 && movies.length===0"> 
       Nessun risultato trovato</h2>

      <MoviesCard :movies="movies" />
      <TVSeriesCard :series="series" />
      
  </main>
</template>

<script>

import MoviesCard from './MoviesCard.vue';
import TVSeriesCard from './TVSeriesCard.vue';

export default {

  components: {
    MoviesCard,
    TVSeriesCard
  },


   data: function(){
        return{

        }
   },

  methods: {

  },

   props: [
    'movies',
    'series',

   ],

   computed: {

   
    
  }

}

</script>

<style>
  main{
    width: 60%;
    margin: 0 auto;
  }

</style>