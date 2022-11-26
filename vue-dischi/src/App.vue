<template>
  <div id="app">
    <HeaderComp />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    HeaderComp
  },
  data(){
    return{
      //tutti i data
    }
  },
  mounted(){
    console.log('ciao');
  },
  // methods(){

  // }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
