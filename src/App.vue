<template>
    <div class="container">
      <div class="serveure">
        <app-header></app-header>
        <hr>
        <div class="row">
            <servers></servers>
            <app-server-details></app-server-details>

        </div>
        <hr>
        <app-footer></app-footer>
        <hr>
      </div>

        <div class="utilisateur">
          <app-user></app-user>

        </div>
        <hr>
        <button class="btn btn-primary" @click="selectcompon = 'appBleu'">Load Bleu Template</button>
        <button class="btn btn-success" @click="selectcompon = 'appVert'">Load Vert Template</button>
        <button class="btn btn-danger" @click="selectcompon = 'appRouge'">Load Rouge Template</button>
        <p>{{selectcompon}}</p>
        <component :is="selectcompon">
        </component>

        <hr>
        <div>
          <!-- <app-Bleu>
            <p>contenu de lla page Bleu!!</p>
          </app-Bleu>
          <app-Vert>
            <p>contenu de lla page Vert!!</p>

          </app-Vert>
          <app-Rouge>
            <p>contenu de lla page R!!</p>

          </app-Rouge> -->


        </div>

    </div>


</template>

<script>
    import Header from './components/Shared/Header.vue';
    import Footer from './components/Shared/Footer.vue';
    import Servers from './components/Server/Servers.vue';
    import ServerDetails from './components/Server/ServerDetails.vue';
    import User from './components/User.vue';
    import Bleu from './components/Bleu.vue';
    import Vert from './components/Vert.vue';
    import Rouge from './components/Rouge.vue';

    export default {
      data: function(){
        return {
          selectcompon:'appBleu'
        }
      },
        components: {
            'app-header': Header,
            'servers': Servers,
            'app-server-details': ServerDetails,
            'app-footer': Footer,
            'app-user': User,
            appBleu: Bleu,
            appVert: Vert,
            appRouge: Rouge
        }
    }
</script>

<style>
.utilisateur {
  background-color: #7EC1E7;
}
.serveure{
  background-color:#F7D4BF;
}


</style>
