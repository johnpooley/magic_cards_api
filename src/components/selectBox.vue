<template lang="html">
  <div class="selectBox">


    <select id="creatureTypes" name="creatureTypes" v-model="value" v-on:change="selectCreature">
      <option value="bird">Bird</option>
      <option value="jellyfish">Jellyfish</option>
      <option value="sheep">Sheep</option>
      <option value="pirate">Pirate</option>
    </select>

  </div>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
  name: 'selectBox',
  data(){
    return{
      value: ''
    }
  },
  components: {
    // "creatureTypes":creatureTypes
  },
  methods: {
    selectCreature: function(){
      console.log("select creature called", this.value);
      eventBus.$emit('selectedCreature', this.value)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
