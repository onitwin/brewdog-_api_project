<template lang="html">
  <li v-on:click="handleClick">{{beer.name}}
    <div id="list-item-style">
      <img :src="beer.image_url">
    </div>
</li>

</template>

<script>
import{eventBus} from '../main.js'
export default {
  name:'list-item',
  props:['beer'],
  methods:{
    handleClick(){
      eventBus.$emit('beer-selected', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
img {
  height: 200px;
}
</style>
