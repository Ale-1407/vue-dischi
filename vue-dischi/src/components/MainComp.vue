<template>
    <main>
        <div class="cont-card w-75 d-flex flex-wrap">
            <CardComp v-for="(elem, index) in dataDischi" 
            :key="index" :card="elem" />
        </div>
    </main>
</template>

<script>

import CardComp from './CardComp.vue';
import axios from 'axios';

export default {
    name: "MainComp",
    components: {
        CardComp
    },
    data(){
        return{
            dataDischi: []
        }
  },
  mounted(){
    this.getInfo();
  },
  methods: {
    getInfo(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( (response) => {
            this.dataDischi = response.data.response
        })
    }
  }
}
</script>

<style lang="scss">

main{
    background-color: #1e2d3b;
}

.cont-card{
    margin: auto;
    padding: 5rem;
    gap: 15px;
}
</style>