<template>
  <section>
       <ul>
             <div>MOVIES</div>

             <section class="movies" v-if="movies.length">
                <li v-for="movie in movies" :key="movie.id">
                <div class="cards">
                    <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.title">
                </div>
                <h5>
                    {{movie.title}} - {{movie.original_title}} - {{movie.original_language}} - {{movie.vote_average / 2 }}
                
                    <lang-flag :iso="movie.original_language"  />

                    <i v-for="n in 5"  :key="n"
                    class="fa-star"  
                    :class ="n <= (Math.ceil(movie.vote_average / 2)) ? 'fas' : 'far' " ></i>
                    
                </h5>
                <p></p>


                </li>

             </section>
        
        </ul>
  </section>
</template>

<script>
export default {
    
    methods: {



  },

   props: [
    'movies',
    'series',

   ],

}
</script>


<style>

</style>