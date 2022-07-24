<template>
  <main>
      <div>
        <div>MOVIES</div>

        <ul>
            <li v-for="movie in movies" :key="movie.id">
              <div class="movie">
                <img src="" alt="">
              </div>
              <h5>
                {{movie.title}} - {{movie.original_title}} - {{movie.original_language}} - {{movie.vote_average}}
            
                  <lang-flag :iso="movie.original_language"  />
                  
              </h5>
              <p></p>

            </li>
        </ul>

      </div>

   

      <div>
        <div> TV SERIES</div>
        <li v-for="serie in series" :key="serie.id">
            <div class="serie">
              <img src="" alt="">
            </div>
            <h5>
              {{serie.name}} - {{serie.original_name}} - {{serie.original_language}} - {{serie.vote_average}}
          
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

  },

   props: [
    'movies',
    'series'
   ]
    
}
</script>

<style>
  main{
    width: 60%;
    margin: 0 auto;
  }

 

</style>