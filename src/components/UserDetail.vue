<template>
  <div class="col-xs-12 ">
    <h1>Tu peux voir les détails de l'utilisateur ICI</h1>
    <p>Nom de l'utilisateur : {{mynom}}</p>
    <p>Votre Adress est  : {{add}}</p>
    <p>Votre Age : {{age}}</p>

    <p>plusieur détails</p>
    <button type="button" @click="restnom">ResetEvent</button>
    <button type="button" @click="restfn()">Resetfunc</button>

    <p>nom inverser : {{mynom}}</p>


  </div>

</template>

<script>
import { eventBus } from '../main';

export default {

  props: {
    mynom: {
      type: String
    },
    add: {
      type: String
    },
    inv: {
      type: String
    },
    age:{
      type: Number
    },
    restfn: Function
  },
  methods:{
    switchnom: function(){
    return this.mynom.split("").reverse().join("");
  },
  restnom: function(){
    this.mynom ='';
    this.add='';
    this.$emit('nomreset', this.nom);
    this.$emit('addreset', this.add);

  },
  creer(){
    eventBus.$on('edage',(age) => {
      this.age = age;
    })
  }
  }

}


</script>
<style scoped>
div {
  border: 1px solid black;
  background-color: coral;
}

</style>
