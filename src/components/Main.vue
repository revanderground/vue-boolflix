<template>
  <main>
    
       
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
      voteIntegers(vote){
            const voteInt = Math.ceil(vote / 2)
            return parseInt(voteInt);
        }
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