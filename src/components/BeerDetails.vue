<template lang="html">
  <div id="chosen-beer" v-if="beer">
    <h3>{{beer.name}}</h3>
    <fave-beers>Favourite</fave-beers>
    <img :src="beer.image_url" height="200px">
    <h3>{{beer.tagline}}</h3>
    <h3>{{beer.description}}</h3>
  </div>

</template>

<script>
import FavouriteBeers from "../components/FavouriteBeers"
export default {
  name:"beer-details",
  props:["beer"],
  components:{
    "fave-beers": FavouriteBeers
  }
}

</script>

<style lang="css" scoped>
</style>
