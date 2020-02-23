<template lang="html">
  <div v-if="card" class="card-detail">
    <h3>Name is {{this.card.name}}</h3>
    <p>{{this.card.flavor}}</p>
    <!-- <img :src="card.image_url" alt="card.name" height=200> -->

    <!-- <div class="fave-on" v-if="!faveBeers.includes(this.card)"> --><br>
    <!-- <button v-on:click="addToFavourites" type="button" name="favourite">Favourite {{card.name}}</button> -->
    <br>
    <!-- </div> -->
    <!-- <button v-on:click="removeFromFavourites" type="button" name="worst">remove {{card.name}} from Favourites</button> -->

  </div>

</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: "card-detail",
  props: ['card'],
  // methods:{
  //   addToFavourites(){
  //     eventBus.$emit('favourited-card', this.card)
  //   },
  //   removeFromFavourites(){
  //     eventBus.$emit('awful-card', this.card)
  //   }
  // }
}
</script>

<style lang="css" scoped>
</style>
