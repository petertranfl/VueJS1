<template>
    <li class="list-group-item"
        style="cursor: pointer"
        @click="loadServerDetails">
      Server #{{ server.id }}
    </li>
</template>

<script>
import {serverBus} from '../../main.js';
    export default {
       props: ['server'],
       methods: {
           loadServerDetails() {
               serverBus.$emit('serverSelected', this.server);
           }
       }
    }
</script>

<style>

</style>
