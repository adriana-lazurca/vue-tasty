<template>
  <b-container>
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.name"
      :image="recipe.image"
      :name="recipe.name"
      :ingredients="recipe.ingredients"
      :instructions="recipe.instructions"
    />
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
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"],
          instructions:
            "Cover and store banana bread at room temperature for 2 days or in the refrigerator for up to 1 week. Banana bread tastes best on day 2 after the flavors have settled together. See post above for freezing instructions."
        },
        {
          name: "Cake",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"],
          instructions:
            "Cover and store banana bread at room temperature for 2 days or in the refrigerator for up to 1 week. Banana bread tastes best on day 2 after the flavors have settled together. See post above for freezing instructions."
        },
        {
          name: "Bread",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"],
          instructions:
            "Cover and store banana bread at room temperature for 2 days or in the refrigerator for up to 1 week. Banana bread tastes best on day 2 after the flavors have settled together. See post above for freezing instructions."
        },
        {
          name: "Crepes",
          image: {
            source: "/images/bananaBread.png",
            alt: "Banana bread"
          },
          ingredients: ["1 cup of sugar", "200ml of milk", "1 egg"],
          instructions:
            "Cover and store banana bread at room temperature for 2 days or in the refrigerator for up to 1 week. Banana bread tastes best on day 2 after the flavors have settled together. See post above for freezing instructions."
        }
      ]
    };
  }
};
</script>

<style></style>
