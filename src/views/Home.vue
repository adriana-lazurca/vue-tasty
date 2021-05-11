<template>
  <b-container>
    <b-row class="">
      <b-col cols="6" v-for="recipe in recipes" :key="recipe.name">
        <Recipe
          :image="recipe.image"
          :name="recipe.name"
          :ingredients="recipe.ingredients"
        />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
// @ is an alias to /src
import Recipe from "../components/Recipe.vue";

export default {
  name: "Home",
  components: {
    Recipe
  },

  data() {
    return {
      restaurantName: "TASTY",

      recipes: [
        {
          name: "Banana bread",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"]
        },
        {
          name: "Cake",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"]
        },
        {
          name: "Bread",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"]
        },
        {
          name: "Crepes",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"]
        }
      ]
    };
  }
};
</script>

<style></style>
