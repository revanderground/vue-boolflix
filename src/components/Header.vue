<template>
  <header class="py-3">

        <div class="container-header">

      <h2 class="brand">
        <img class="logo" src="../assets/img/logo-boolfilx.png" alt="logo">
      </h2>

      <div class="searchbar">
        <input type="text" v-model="needle">
        <button @click="$emit('movieSearch', needle)">Cerca</button>
    
      </div>

    </div>


  </header>

    
</template>

<script>
export default {
  data: function(){
    return{
      needle:'',
    }
  }
}
</script>

<style lang="scss" scoped>



  header{
    background-color: black;
    height: 15vh;;

  }
  
  .container-header{
    width: 95%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }  

  .logo{
    width: 150px;
  }

  .searchbar{
    padding-right: 50px;
  }




</style>