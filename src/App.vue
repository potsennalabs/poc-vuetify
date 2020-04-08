<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      dark
    >
      <div class="d-flex align-center primary--text">
        <v-btn icon @click="drawer = true">
          <v-icon color="primary">mdi-menu</v-icon>
        </v-btn>
        <b>TEAM HERO</b>
      </div>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon color="#e4e4e6">mdi-bell</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <HelloWorld/>
      <v-navigation-drawer
        v-model="drawer"
        absolute
      >
        <v-list
          nav
          dense
        >
          <v-list-item-group
            v-model="group"
            active-class="deep-purple--text text--accent-4"
          >
            <v-list-item>
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Profile</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Check-in</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Members</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-title>Ranks</v-list-item-title>
            </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    drawer: false,
    group: null,
  }),

  watch: {
    group () {
      this.drawer = false
    },
  },
};
</script>

<style scoped>
.v-toolbar {
  box-shadow: 0 3px 30px 0 rgba(99, 161, 213, 0.09);
}

aside.v-navigation-drawer {
  width: 100% !important;
}
</style>
