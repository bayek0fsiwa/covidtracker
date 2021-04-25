<template>
  <!-- card 1 -->
  <div>
    <div>
      <h3>Cases</h3>
      <span>New: </span>
      <h2>{{ numberWithCommas(stats.NewConfirmed) }}</h2>
      <div>
        <span>Total: </span>
        <h2>{{ numberWithCommas(stats.TotalConfirmed) }}</h2>
      </div>
    </div>
    <!-- card 2 -->
    <div>
      <h3>Deaths</h3>
      <span>New: </span>
      <h2>{{ numberWithCommas(stats.NewDeaths) }}</h2>
      <div>
        <span>Total: </span>
        <h2>{{ numberWithCommas(stats.TotalDeaths) }}</h2>
      </div>
    </div>
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