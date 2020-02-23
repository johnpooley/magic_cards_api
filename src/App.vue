<template lang="html">
  <div class="mainPage">
    <p>hello magic players</p>
    <p>choose a creature type</p>
    <select-box />

    <card-list :cards="cards"/>


  </div>

</template>

<script>

import {eventBus} from './main.js'
import faveCards from './components/faveCards.vue'
import listOfCards from './components/listOfCards.vue'
import selectBox from './components/selectBox.vue'
import selectedCard from './components/selectedCard.vue'

export default {
  name: 'app',
  components: {
    "select-box": selectBox,
    "card-list":listOfCards

  },
  data(){
    return{
      cards:[],
      cardNames:[],
      cardArray:[],
      cardType:''
    }
  },
  methods: {


    fetchData: function(creature){
      // const removeDupes= function (array) {
      //   const nameOnly = array.map(name => array.name);
      //   cardNames.push(nameOnly);
      //   return cardNames.filter((a, b)=> arrayindefOf(a) == b)
      // };
      fetch('https://api.magicthegathering.io/v1/cards?subtypes='+creature)
      .then(result => result.json())
      .then(cards => this.cards = cards)
      // .then(removeDupes(cards.cards))
    },



    // console.log(creature);

  },

  mounted(){
    eventBus.$on('selectedCreature', (creature) => this.fetchData(creature))

  },

}



</script>

<style lang="css" scoped>
</style>
