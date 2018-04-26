<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please choisir un serveur</p>
        <p v-else>Serveur #{{server.id}} selectioner, Status: {{server.status}}</p>
    </div>

</template>

<script>
import {serverBus} from '../../main';
export default {
  data: function(){
    return {
      server: null
    }
  },
  created(){
    serverBus.on('serverselect', (server) => {
      this.server = server;
    })
  }
}
</script>

<style scoped>
div {
  border: 1px solid red;
}

</style>
