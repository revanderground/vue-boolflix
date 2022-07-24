<template>
  <div id="app">
    <Header @movieSearch="getMovies" />
    <Main :movies="movies" />
  
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
            apiUrl: 'https://api.themoviedb.org/3/search/movie',
            // api_key=6316d39114a3b497a4434be7beba0ccf&language=en-US&query=prova&page=integer
            movies: [],
        }

  },

  methods: {
    getMovies(needle){
      axios.get(`${this.apiUrl}?api_key=${this.apiKey}&query=${needle}`)
      .then((result) => {
        console.log(result.data.results);
        this.movies = result.data.results;
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
