<template>
  <div class="layout">
    <v-navigation-drawer
      v-model="drawer"
      fixed
      app
      color="warning"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app color="warning">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn href="https://www.covid19api.org/" target="_blank">
      <v-icon>notranslate mdi mdi-virus theme--light</v-icon>
      API
      </v-btn>
    </v-app-bar>
    <v-footer app color="warning">
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      fixed: true,
      items: [
        {
          icon: "mdi-apps",
          title: "Home",
          to: "/",
        },
        {
          icon: "mdi-graph",
          title: "Graph",
          to: "/graph",
        },
      ],
      title: "Covid 19 smh!",
    };
  },
};
</script>