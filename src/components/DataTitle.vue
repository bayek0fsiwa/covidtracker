<template>
  <div class="data-title">
      <v-card elevation="5">
        <v-card-title>
            {{text}}
        </v-card-title>
        <v-card-subtitle>
            {{dataDate}}
        </v-card-subtitle>
      </v-card>
  </div>
</template>

<script>
import moment from "moment";
export default {
    name: 'DataTitle',
    props: ['text', 'dataDate'],
    computed: {
        timestamp: function() {
            return moment(this.dataDate).format('MMMM Do YYYY h:mm:ss a')
        }
    }
}
</script>

<style>

</style>