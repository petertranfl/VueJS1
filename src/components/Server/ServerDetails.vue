<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please Select a Server</p>
        <p v-else>Server #{{server.id}}// Server Status: {{server.status}}</p>
        <hr>
        <button @click="resetServerStatus">Reset Server Status</button>
    </div>

</template>

<script>
    import {serverBus} from '../../main.js';

    export default {
        data: function() {
            return {
                server: null
            };
        },
        methods: {
            resetServerStatus() {
                this.server.status = "Normal";
            }
        },
        created() {
            serverBus.$on('serverSelected', (server) => {
                this.server = server
            });
        }
    }
</script>

<style>

</style>
