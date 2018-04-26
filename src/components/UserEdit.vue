<template>
  <div class="col-xs-12">
    <h1>Tu peux modifier l'utilisateur</h1>
    <p>Modifier</p>
    <input type="text" :value="agee" placeholder="Entre votre Age">
    <button type="button" @click='ajoutage'>Ajouter Age</button>
    <p>{{age}}</p>

  </div>

</template>

<script>
import { eventBus } from '../main';

export default {
  data: function(){
    return {
    }
  },
  props:{
    age:{
      type: Number
    },
    agee:{
      type: String
    }
  },
  methods: {
    ajoutage: function() {
      this.age = 27;
      this.$emit('edage', this.age);
      //eventBus.$emit('edage', this.age);
      //eventBus.changerage(this.age);

    }
  }
}

</script>
<style scoped>
div {
  border: 1px solid blue;
  background-color: Yellow;
}

</style>
