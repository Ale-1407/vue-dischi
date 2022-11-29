<template>
    <main>
        <div class="text-left p-3 ">
            <select name="" id="" v-model="optionGenere" class="rounded-4 p-1">
                <option :value="elem" v-for="(elem, index) in arrayGeneri" :key="index">{{elem}}</option>
            </select>
        </div>
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
            dataDischi: [],
            optionGenere: '',
            arrayGeneri: []
        }
  },
  mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( (response) => {
            //inserisco tutte le informazioni dentro array dataDischi
            this.dataDischi = response.data.response
            //ciclo su array di dischi
            this.dataDischi.forEach( (singoloAlbum) => {
                //condizione con includes per controllare se nell'array dei generi è 
                //già presente il genere che voglio pushare
                if( !this.arrayGeneri.includes(singoloAlbum.genre)){
                    this.arrayGeneri.push(singoloAlbum.genre)
                }
            })
            
        })

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
    gap: 20px;
}
</style>