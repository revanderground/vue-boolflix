<template>
  <div id="app">
    <Header @movieSearch="getMoviesAndSeries" />
    <Main :movies="movies" :series="series"  />

    
  
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main
  },

  data: function(){
        return{
            apiKey: "6316d39114a3b497a4434be7beba0ccf",
            apiMovieUrl: 'https://api.themoviedb.org/3/search/movie',
            apiTVSeriesUrl: 'https://api.themoviedb.org/3/search/tv',
            
            // api_key=6316d39114a3b497a4434be7beba0ccf&language=en-US&query=prova&page=integer
            movies: [],
            series: [],
        }

  },

  methods: {

    getMoviesAndSeries(needle){
      // call server for Movies search
      axios.get(`${this.apiMovieUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then((result) => {
        console.log(result.data.results);
        this.movies = result.data.results;
      })
      .catch((error) =>{
        console.warn(error)
      })
   
       // call server for TV Series search
      axios.get(`${this.apiTVSeriesUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then((result) => {
        console.log(result.data.results);
        this.series = result.data.results;
      })
      .catch((error) =>{
        console.warn(error)
      })
    }


  }
}
</script>

<style lang="scss">

</style>
