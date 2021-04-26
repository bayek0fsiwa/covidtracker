<template>
  <div class="home">
    <v-container>
      <v-main  v-if="!loading">
        <DataTitle :text="title" :dataDate="dataDate" />
        <DataCards :stats="stats" />
        <Countries :countries="countries" />
      </v-main>
      <v-main  v-else>
        <h2>Loading Data</h2>
        <img :src="loadingImage">
      </v-main>
    </v-container>
  </div>
</template>

<script>
import DataTitle from '@/components/DataTitle'
import DataCards from '@/components/DataCards'
import Countries from '@/components/Countries'

export default {
  name: 'Home',
  data() {
    return {
    url: 'https://api.covid19api.com/summary',
    loading: true,
    title: 'Global',
    dataDate: '',
    stats: {},
    countries: [],
    loadingImage: require('../assets/logo.png')
    }
  },
  components: { DataTitle, DataCards, Countries },
  methods: {
    async covidData() {
      const response = await fetch('https://api.covid19api.com/summary')
      const data = await response.json()
      return data
    }
  },
  async created() {
    const data = await this.covidData()
    this.dataDate = data.Date
    this.stats = data.Global
    this.countries = data.Countries 
    this.loading = false
  },
}
</script>
