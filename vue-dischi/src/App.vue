<template>
  <div id="app">
    <HeaderComp />
    <MainComp />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import axios from 'axios';
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      
    }
  },
  mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then( (response => {
        console.log(response.data.response)
      }) )
  },
  // methods(){

  // }
}
</script>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100vh;
  }
</style>
