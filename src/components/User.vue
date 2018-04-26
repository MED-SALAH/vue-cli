<template >
  <div class="component">
    <h1>Les composent de l'utilisateur</h1>
    <h4>Je suis l'utilisateur</h4>
    <ul>
      <li>
        <input type="text" v-model:value="vide" placeholder="Entrer votre nom">
        <button type="button" @click="changerNom">Changer mon Nom</button>

      </li>
      <li>
        <input type="text" v-model:value="adres" placeholder="Entrer votre Adresse">
        <button type="button" @click="ajoutadr">Ajouter une Adresse</button>

      </li>

    </ul>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <app-user-detail
        :mynom="nom"
        :add="add"
        :age="age"
        :agee="agee"
        @nomreset="nom = $event"
        @addreset="add = $event"
        :restfn = "restf">

        </app-user-detail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <app-user-edit :age="age" @edage="age =$event"></app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue';
import UserEdit from './UserEdit.vue';

export  default {
  data: function() {
    return  {
      nom : '',
      vide:'',
      add:'',
      adres:'',
      inv:'',
      age:'',
      agee:''
    };
  },
  methods: {
    changerNom: function(){
      this.nom = this.vide;

    },
    ajoutadr: function(){
       this.add = this.adres;
    },
    resetf: function(){
      this.nom ='';
    }

  },
  components : {
    'app-user-detail': UserDetail,
    'app-user-edit': UserEdit,
  }
}
</script>
<style scpoer>
h1 {
  text-align: center;
}
</style>
