<template>
<div>
  <select v-model="selected" @change="onChange">
  <option value="0">Select Country</option>
  <option v-for="country,i in countries" :key="i" :value="country.ID">{{ country.Country }}</option>
  </select>
</div>
</template>

<script>
export default {
    name: 'Countries',
    props: ['countries'],
    data() {
        return {
            selected: 0
        }
    },
    methods: {
        onChange() {
            const country = this.countries.find((item) => item.ID === this.selected)
            this.$emit('get-country', country)
        }
    }
}
</script>

<style>

</style>