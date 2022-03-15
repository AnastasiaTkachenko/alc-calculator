<template>
  <div class="c-game">
    <header>

      <v-btn to="/cocktailCreator"
          class="ma-2"
          outlined
          color="yellow lighten-1"
          x-large
      > COCKTAILMAKER
      </v-btn>
      <v-btn to="/"
             class="ma-2"
             outlined
             color="yellow lighten-1"
             x-large
      > MAIN
      </v-btn>

  
    </header>

<div class="divider">
  <v-divider light >
  </v-divider>
</div>

    <h2 class="question">{{ question }}</h2>
    <div class="buttons">
      <v-btn
          rounded
          x-large
          elevation="2"
          @click="nextQuestion(true)" color="yellow lighten-1 mb-4">YES</v-btn>
      <v-btn rounded
             x-large
             elevation="2"
             @click="nextQuestion(false)" color="yellow lighten-1">NO</v-btn>


    </div>
    <div class="recommendation">
      <p v-if="selectedDrink">{{ answer }}</p>
      <img class="photoCocktail" v-if="selectedDrink" :src="selectedDrink.strDrinkThumb"/>
      <!--;v-if="selectedDrink пишем чтобы оно не высвесиыалсь когда заходишь на станцу так
      как приписано селекетед дринк нул -
      v-if= внутри долждно быть условие, если это условие верно, то отобращится таг к оторому
      в иф приписан, если не верно то не будет тага вообще
-->
    </div>



  <div class="recepie-button">
      <template>
        <div class="text-center">
          <v-bottom-sheet
              v-model="sheet"
              persistent
          >
      <template v-slot:activator="{ on, attrs }">
              <v-btn
                  class="ma-2"
                  outlined
                  color="yellow lighten-1"
                  x-large
                  v-bind="attrs"
                  v-on="on"
              >
                RECIPE OF SUGGESTED COCKTAIL
              </v-btn>
            </template>
            <v-sheet
                class="text-center"
                height="200px"
            >
              <v-btn
                  class="mt-6"
                  text
                  color="error"
                  @click="sheet = !sheet"
              >
                close
              </v-btn>
              <div class="py-3">
               Here will be the recipe of the suggested cocktail.
              </div>
            </v-sheet>
          </v-bottom-sheet>
        </div>
      </template> 
      </div>
     <Footer/>
      </div>


</template>

<script>
import Footer from "@/components/Footer";
export default {
  name: 'Game',
  components : {
  Footer,
  },
  data() {
    return {
      questions: ['Are you in a happy mood?',
        'Do you like magic?',
        'Fancy day drinking?'
      ],
      currentQuestion: 0,
      selectedDrink: null,
      answer:"",
      sheet:false,
    }
  },
  computed: {  /*это способ чтобы сдифинировта;(создать) переменую, квксшен и ансвер это переменные,
    если чтото из этого изменитьмя то квсшен тоже изменться, компьютед постоянно проверяет ничего ли не изменилось
     и если изменилось то пересчитывает*/
    question() {
      return this.questions[this.currentQuestion]
    },

  },
  methods: {  /*тут чисто функции они сами по себе не выпоняюися, в эйчижмле мы говорим что мы хотим чтото */
    async nextQuestion(positive) {
      this.currentQuestion = this.currentQuestion < 2 ? this.currentQuestion + 1 : this.currentQuestion;
      await this.getRandomDrink();
      this.answer=positive ? 'You are my favorite person! The drink that will make magic for you today is ' + this.selectedDrink.strDrink :
          `You are upsetting me! ${this.selectedDrink.strDrink} will cheer you up!`


    },
    async getRandomDrink() {
      let response = await fetch("https://thecocktaildb.com/api/json/v1/1/random.php");
      const data = await response.json();
     this.selectedDrink=data.drinks[0];
    },

   /* async getCocktailByIngredients() {
      let response = await fetch ("https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=Gin");
      const i = await response.json();

      console.log(i);
          }*/
  },


}
</script>
<style lang="scss" scoped>
.c-game {
  background: rgba(0, 0, 0, 0.45);
  height: 100vh;
  width: 100vw;
  position: absolute;
  top: 0;
  backdrop-filter: blur(35px);
}

header {
  display: flex;
  width: 100%;
  flex-direction: column;
  justify-content: center;
 
  @media (min-width: 768px) {
    width:100%;
    flex-direction: row;
    height: 100px;

  }
  @media (min-width: 1024px) {
   height: 200px;
  }
}  


.question {
  font-weight: normal;
  font-size: 48px;
  line-height: 59px;
  text-transform: uppercase;
  text-align: center;
  color: #fff;

}

.buttons {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-top: 50px;
  @media (min-width: 768px) {
    flex-direction: row;
    margin: 50px auto;
  }
  @media (min-width: 1024px) {
    margin: 60px 300px;
  }

  .v-btn {
    padding: 1.5rem;
    width: 70%;
    margin: 0 auto;
    @media (min-width: 768px) {
      width: 35%;
    }
    @media (min-width: 1024px) {
      margin: 0 1rem;

      min-width: 20rem;
    }
  }
}

.divider {
  display:none; 
  @media (min-width: 1024px) {
    display: block;
  }
}
header .v-btn {


@media (min-width: 1024px) {
  width:400px;
  margin: auto 25px !important;
}

}

header {
  padding: 50px 0px;
  @media (min-width: 1024px) {
  padding: 0px;
  }
}



.recommendation {
  width: 100%;
  color: #fff;
  text-align: center;
  padding: 2rem;
  font-size: 1.5rem;
  line-height: 2rem;
  @media (min-width: 768px) {
    font-size: 2rem;
    line-height: 2.5rem;
  }
  @media (min-width: 1024px) {
    font-size: 2.5rem;
    line-height: 3.5rem;
    padding: 2rem 22rem;

  }
}

.photoCocktail {
  height: 300px;
  width: 300px;

}

.divider {
  margin-bottom: 80px;
 background-color: #9e9e9e;
}


.recepie-button .v-btn{
width:90%;
  @media (min-width: 1024px) {
  margin:50px; 
  width: 400px;
  }
}
</style>