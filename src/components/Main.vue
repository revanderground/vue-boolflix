<template>
  <main>
    <ul>
      <li v-for="movie in movies" :key="movie.id">
          <div class="movie">
            <img src="" alt="">
          </div>
          <h5>
            {{movie.title}} - {{movie.original_title}} - {{movie.original_language}} - {{movie.vote_average}}
          </h5>
          
      </li>
    </ul>
 
  </main>
</template>

<script>
export default {
   data: function(){
        return{

        }
   },
   props: [
    'movies'
   ]
    
}
</script>

<style>
  main{
    width: 60%;
    margin: 0 auto;
  }

</style>