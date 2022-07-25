<template>
  <section>
       <ul>
             <div>MOVIES</div>
            <li v-for="movie in movies" :key="movie.id">
              <div class="movie">
                <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.title">
              </div>
              <h5>
                {{movie.title}} - {{movie.original_title}} - {{movie.original_language}} - {{movie.vote_average / 2 }}
            
                  <lang-flag :iso="movie.original_language"  />
                  <font-awesome-icon icon="fa-solid fa-star" v-for="(star,index) in voteIntegers(movie.vote_average)" :key="index"/>
                  
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