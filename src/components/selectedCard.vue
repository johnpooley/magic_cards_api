<template lang="html">
  <option v-on:click="showDetails">{{card.name}}, from the set {{card.set}} </option>


</template>

<script>

import {eventBus} from '../main.js';

export default {
  name: 'card-list-item',
  props: ['card'],
  methods: {
    showDetails(){
      eventBus.$emit('card-selected', this.card)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
