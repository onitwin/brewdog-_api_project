<template lang="html">
  <div>
    <button v-on:click="faveClick">Favourite</button>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  name:"fave-beers",
  props:["beer"],
  methods:{
    faveClick(){
      eventBus.$emit('fave-beers',this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
