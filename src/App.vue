<template>
  <v-app>
    <v-content>
      <router-view></router-view>
    </v-content>
    <v-footer
      color="primary lighten-1"
      padless
      app
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-col
          class="primary lighten-2 py-4 text-center white--text"
          cols="12"
        >
          <strong>Etickette</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    links: [
      'Home',
      'About',
      'Impressum',
    ],
  }),
};
</script>
