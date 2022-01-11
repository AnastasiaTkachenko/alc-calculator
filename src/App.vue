<template>

  <div id="app">

<v-app id="main">

 <div class="container">


          <!--HEADING -->
   <h1 class="text-center">
     FANCY <br> DRINKING?
   </h1>


<!--BUTTONS -->

  <v-btn class="button1" block color="yellow darken-1">
    GO TO QUESTIONS
  </v-btn>

  <v-btn class="button2" block color="yellow darken-1">
    GO TO ALCOHOL CALCULATOR
  </v-btn>


<div class="text">
   <h2 class="text-center">
     answer a question and let the universe lead you to the
   </h2>

   <h2 class="text-center" >
     🎉  PERFECT DRINK OF THE DAY  🎉
   </h2>
</div>

<!--   FOOTER -->
   <v-footer bottom fixed padless>
     <v-col
         class="text-center"
         cols="12"
     >
       {{ new Date().getFullYear() }} — <strong>Cheeers!</strong>
     </v-col>
   </v-footer>




 </div>



</v-app>





</div>




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

@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300&display=swap');


.container {
  background-image:url('assets/img/duck.jpg');
  background-repeat: no-repeat;
  background-position: center;
  min-width: 100%;
  min-height: 100%;



}

.container .button1 {
  margin-top: 400px;
}

.v-btn {
 margin-top: 20px;

}


h1 {
  position: absolute; // for central text we use width:100%; left:0px;
  top:2em;
  font-size:4rem;
  font-family: Lato,sans-serif;
  width:100%; left:0px;
  letter-spacing: 20px;

}

h2 {
  font-family: Lato, sans-serif;
  position: relative; // using for not pushing everything down
  top: 5em;
  margin-top:8px;


}



</style>