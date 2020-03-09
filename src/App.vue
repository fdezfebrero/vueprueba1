<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <h1>Lista de Participantes</h1>

      <v-spacer></v-spacer>


    </v-app-bar>

    <v-content>
      <Listapp/>
    </v-content>
  </v-app>
</template>

<script>
import Listapp from './components/Listapp';
/*import participants from './participants.json';*/

export default {
  name: 'App',

  components: {
    Listapp,
  },

  data: () => ({
    //
  }),
};
</script>
