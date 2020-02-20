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
  display: inline-block;
  border: 10px double blue;
  width:300px;
  height:300px;
  align-content: center;
  padding-top: 50px;
  margin:20px;
  border-radius: 40px;
  font-size: 14pt;

}

</style>
