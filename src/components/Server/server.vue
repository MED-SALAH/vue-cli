<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <li class="list-group-item" style="cursor: pointer"
            @click="serverselect">Server #{{ server.id }}</li>
        </ul>
    </div>
</template>

<script>
import {serverBus} from '../../main'
export  default {
  props: ['server'],
  methods:{
    serverselect(){
      serverBus.$emit('serverselect', this.server);
    }
  }

}
</script>

<style scoped>
div {
  border: 1px solid blue;
}

</style>
