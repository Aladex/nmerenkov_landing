<template>
  <v-app>
    <v-main>
      <StartPage/>
    </v-main>
  </v-app>
</template>

<script>
import StartPage from './components/StartPage';

export default {
  name: 'App',

  components: {
    StartPage,
  },

  data: () => ({
    //
  }),
  created () {
    document.title = "Николай Меренков";
  }
};
</script>
