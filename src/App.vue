<template>
  <div id="app">
    <h1>Brewdog</h1>
    <beer-details :beer="selectedBeer"></beer-details>
    <list-of-beers :beers="beers"></list-of-beers>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import BeerList from './components/BeerList.vue';
import BeerDetails from './components/BeerDetails'
import FavouriteBeers from './components/FavouriteBeers'

export default {
  name: 'App',
  data(){
    return{
      beers:[],
      selectedBeer:null,
      favouriteBeers:[]
    }
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res =>res.json())
    .then(data => this.beers=data)

  eventBus.$on('beer-selected', (beer)=>{
    this.selectedBeer=beer;

  eventBus.$on('fave-beer', (beer)=>{
    this.favouriteBeers.push(beer)
  })
  })
  },
  components:{
    "list-of-beers":BeerList,
    "beer-details":BeerDetails
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
