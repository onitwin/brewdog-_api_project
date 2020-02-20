<template>
  <div id="app">
    <h1>Brewdog</h1>
    <list-of-beers :beers="beers"></list-of-beers>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeerList from './components/BeerList.vue';

export default {
  name: 'App',
  data(){
    return{
      beers:[],
      selectedBeer:null
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res =>res.json())
    .then(data => this.beers=data)

  eventBus.$on('beer-selected')
  },
  components:{
    "list-of-beers":BeerList
  },
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
