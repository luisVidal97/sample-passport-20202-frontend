<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark

    >
      <div class="d-flex align-center">
       

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn4.iconfinder.com/data/icons/shopping-marts-and-malls/1000/4-512.png"
          width="100"
          height="50"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/luisVidal97"
        target="_blank"
        text
      >
        <span class="mr-2">Repositorio github</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
    <br>
    <br>
    <router-view></router-view>
  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {
 
  },

  data: () => ({
    //
  }),
};
</script>
