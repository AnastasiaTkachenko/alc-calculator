<template>

  <div class="c-cocktailCreator">

    <ul class="selectedIngredients">
      
      <!-- inline object literal -->
      <li :class=" [  selectedIngredients.indexOf(ingredient) === -1 ?  'ingredient' : 'selectedIngredient ingredient']"
          @click="selectIngredient(ingredient)" :key="ingredient" v-for="ingredient in ingredients"> {{ ingredient }}
      </li>
    </ul>


  </div>

</template>


<script>

export default {
  data: () => ({
    ingredients: [
      'Amaretto',
      'Apple juice',
      'Blackberry brandy',
      'Blended whiskey',
      'Bourbon',
      'Brandy',
      'Campari',
      'Champagne',
      'Cherry',
      'Coca-Cola',
      'Coffee',
      'Dry Vermouth',
      'Gin',
      'Ice',
      'Lemon',
      'Lemon juice',
      'Lime',
      'Milk',
      'Mint',
      'Orange juice',
      'Pineapple juice',
      'Rum',
      'Salt',
      'Soda water',
      'Sugar',
      'Tequila',
      'Triple sec',
      'Vanilla',
      'Vermouth',
      'Vodka',
    ],
    selectedIngredients: [],


  }),

  computed: {},

  methods: {
    selectIngredient(ingredient) {
      if (this.selectedIngredients.indexOf(ingredient) === -1) {
        this.selectedIngredients.push(ingredient);
      } else {
        this.selectedIngredients = this.selectedIngredients.filter(el => el !== ingredient);

      }
    }
  }

}


</script>

<style lang="scss" scoped>
.c-cocktailCreator {
  background: rgba(0, 0, 0, 0.45);
  height: 100vh;
  width: 100vw;
  position: absolute;
  top: 0;
  backdrop-filter: blur(35px);
}

.v-select {
  font-size: 1.2em;
}

.selectedIngredients {
  height: 500px;
  width: 600px;
  border: 1px solid white;
list-style: none;
  overflow: auto;
  background-color:#ffc400;

}

.ingredient {
 cursor:pointer;
  font-size: 20px;
  background-color:#ffc400;
  padding: 10px;

}

.selectedIngredient {
  background-color: blue;
}

</style>