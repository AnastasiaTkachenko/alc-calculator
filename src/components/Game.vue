<template>
<div id="app">
  <v-app id="main">

    <div class="container">


      <div id="round-botton">
          <v-row justify="space-around">
            <v-menu
                bottom
                origin="center center"
                transition="scale-transition"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                    class="mx-2"
                    fab
                    dark
                    large
                    color="yellow darken-1"
                    v-bind="attrs"
                    v-on="on"
                >
                  <v-icon dark>
                    mdi-plus
                  </v-icon>
                </v-btn>
              </template>

              <v-list>
                <v-list-item
                    v-for="row in 2"
                    :key="row"
                    @click="() => {}"
                >
<v-text-field to="/Home" v-text="'MAIN'"
                  </v-text-field>

                  <!--                  <v-list-item-title to="/Home" v-text="'MAIN'"></v-list-item-title>-->

                </v-list-item>
              </v-list>
            </v-menu>

          </v-row>


      </div>

    </div>






    </v-app>



</div>
</template>

<script>

// new Vue({
//   el: '#app',
//   vuetify: new Vuetify(),
//   data: () => ({
//     items: [
//       { title: 'Click Me' },
//       { title: 'Click Me' },
//       { title: 'Click Me' },
//       { title: 'Click Me 2' },
//     ],
//   }),
// })

export default {
  name: "Game"

}
</script>

<style scoped>

</style>