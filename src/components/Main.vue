<template>
  <main>
      <div>
        <div>MOVIES</div>

        <ul>
            <li v-for="movie in movies" :key="movie.id">
              <div class="movie">
                <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.title">
              </div>
              <h5>
                {{movie.title}} - {{movie.original_title}} - {{movie.original_language}} - {{movie.vote_average}}
            
                  <lang-flag :iso="movie.original_language"  />
                  <font-awesome-icon icon="fa-solid fa-star" v-for="(star,index) in voteIntegers(movie.vote_average)" :key="index"/>
                  
              </h5>
              <p></p>

            </li>
        </ul>

      </div>

   

      <div>
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

      </div>
  
    
    

  </main>
</template>

<script>
export default {
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