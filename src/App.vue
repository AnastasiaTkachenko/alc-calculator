<template>

<v-app>
 <div class="container">
  <v-btn block color="yellow darken-1">
    GO TO QUESTIONS
  </v-btn>

  <v-btn block color="yellow darken-1">
    GO TO ALCOHOL CALCULATOR
  </v-btn>


 </div>
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

<style lang="scss">


.container {
  background-image:url('assets/img/duck.jpg');
  background-repeat: no-repeat;
  background-position: center;
  width: 100vw;
  height: 100vh;

}



</style>