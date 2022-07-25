<template>
  <section>
    <ul>
         <div> TV SERIES</div>
         <li v-for="serie in series" :key="serie.id">
            <div class="serie">
              <img :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`" :alt="serie.name">
            </div>
            <h5>
              {{serie.name}} - {{serie.original_name}} - {{serie.original_language}} - {{serie.vote_average / 2}}
              <font-awesome-icon icon="fa-solid fa-star" v-for="(star,index) in voteIntegers(serie.vote_average)" :key="index"/>
              
          
              <lang-flag :iso="serie.original_language"  />
              
              
            </h5>
            <p></p>

        </li>

    </ul>
    
  </section>
</template>

<script>
export default {

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


}
</script>

<style>

</style>