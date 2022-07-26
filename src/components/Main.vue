<template>
  <main>
    <div class="container.fluid">

      <h2 v-if="series.length===0 && movies.length===0"> 
       Nessun risultato trovato</h2>
      
      <div class="cards">
        <Cards :movies="movies" :series="series"  />
      </div>



    </div>

      
  </main>
</template>

<script>

import Cards from './Cards.vue';


export default {

  components: {
    Cards,
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

  .container.fluid{
    margin: 0 auto;

  }

  .cards{
    height:calc(85vh - 47px);
  }


 
</style>