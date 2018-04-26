<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
          <app-Server v-for="server in servers"
          :server="server"></app-Server>
        </ul>
    </div>
</template>

<script>
import Server from './server.vue'
export  default {
  data: function(){
    return {
      servers: [
        {id:1, status: 'Normale'},
        {id:2, status: 'Critical'},
        {id:3, status: 'Unknown'},
        {id:4, status: 'Normale'}

      ]
    };
  },
  components: {
    'app-Server': Server
  }
}
</script>

<style scoped>
div {
  border: 1px solid blue;
}

</style>
