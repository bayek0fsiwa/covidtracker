<template>
  <!-- card 1 -->
  <div>
    <v-card elevation="5">
      <v-card-title>
        Cases
      </v-card-title>
      <span>New: </span>
      <v-card-content>
            {{ numberWithCommas(stats.NewConfirmed) }}
      </v-card-content>
      <span>Total: </span>
      <v-card-content>
            {{ numberWithCommas(stats.TotalConfirmed) }}
      </v-card-content>
    </v-card>
    </div>
</template>

<script>
export default {
  name: "DataCards",
  props: ["stats"],
  methods: {
      numberWithCommas(x) {
          return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
      }
  }
};
</script>

<style>
</style>