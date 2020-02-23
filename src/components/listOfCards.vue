<template lang="html">
  <ul>
    <card-list-item v-for ="(card, index) in cards.cards"  :card="card" :key="index"/>

  </ul>

</template>

<script>

import cardItem from './selectedCard.vue'
export default {
  name: 'card-list',
  props:['cards', 'cardNames'],
  components:{
    "card-list-item": cardItem,
  }
}
</script>

<style lang="css" scoped>
</style>
