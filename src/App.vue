<template>
  <v-app>
    <Layout />
    <v-content>
       <router-view />
    </v-content> 
  </v-app>
</template>

<script>
import Layout from './components/Layout';

export default {
  name: 'App',
  components: { Layout },
  data: () => ({
    //
  }),
};
</script>
