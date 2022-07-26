<template>
  <main>
    <div class="container">

      <h2 v-if="series.length===0 && movies.length===0"> 
       Nessun risultato trovato</h2>

      <MoviesCard :movies="movies" />
      <TVSeriesCard :series="series" />


    </div>

      
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

<style lang="scss" scoped>
  *{
    background-color: rgb(5, 68, 95);

  }

  .container{
    width: 60%;
    margin: 0 auto;
    height:calc(100vh - 15vh);
    

  }


 
</style>