<template>
  <div class="data-title">
      <h2>{{text}}</h2>
      <div>
          {{dataDate}}
      </div>
  </div>
</template>

<script>
export default {
    name: 'DataTitle',
    props: ['text', 'dataDate'],
}
</script>

<style>

</style>