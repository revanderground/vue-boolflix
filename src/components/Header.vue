<template>
  <header>
    <h2>
      Boolflix
    </h2>

    <div>
      <input type="text" v-model="needle">
      <button @click="$emit('movieSearch', needle)">Cerca</button>
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

<style>
  header{
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

</style>