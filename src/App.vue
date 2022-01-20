<template>
  <v-app>
    <v-main>
<Game />
      <router-view/>

    </v-main>
  </v-app>
</template>

<script>

import Game from './components/Game'
export default {
  name: 'App',
  components: {
    Game,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">


</style>