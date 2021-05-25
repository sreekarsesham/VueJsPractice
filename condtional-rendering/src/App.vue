<template>
  <h2 v-if="num === 0">The number is 0</h2>
  <h2 v-else>The number {{num}}</h2>
  <h2 v-show="showElement">using v-show</h2>
  <h2 v-show="showElement">showing using v-if</h2>
</template>

<script>

export default {
  name: 'App',
  data(){

    return{

      num:12345624,
      showElement:true,

    }
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
