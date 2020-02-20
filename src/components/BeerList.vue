<template lang="html">
  <div>
  <ul>
    <list-item v-for="(beer,index) in beers" :beer="beer" :key="index"></list-item>
  </ul>
</div>

</template>

<script>
import BeerItem from './BeerItem.vue'
export default {
  name:'list-of-beers',
  props:['beers'],
  components:{
    "list-item":BeerItem
  }
}
</script>

<style lang="css" scoped>
li{
  list-style-type: none;
}
</style>
