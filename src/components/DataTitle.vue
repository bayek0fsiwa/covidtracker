<template>
  <div class="data-title">
      <h2>{{text}}</h2>
      <div>
          {{dataDate}}
      </div>
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