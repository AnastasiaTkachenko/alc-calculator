<template>
  <v-app>
    <v-main>
      <router-view/>

    </v-main>
  </v-app>
</template>

<script>


export default {
  name: 'App',
};
</script>

<style lang="scss">
.v-application {
  background-size: cover !important;
  background: url('assets/img/duck.jpg') no-repeat center !important;
  -webkit-background-size:100% !important;
  @media (min-width: 768px) {
    background: url('assets/img/duck.jpg') no-repeat center !important;
    -webkit-background-size:auto !important;
    background-size: cover !important;

  }
}

</style>