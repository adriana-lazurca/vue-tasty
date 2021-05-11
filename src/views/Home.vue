<template>
  <b-container>
    <b-row>
      <b-col offset-sm="10"
        >{{ totalLikes }} recipes
        <b-icon class="h5 mb-0" icon="heart-fill"></b-icon
      ></b-col>
    </b-row>
    <h1 class="mt-5">Welcome to {{ restaurantName }}</h1>
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.name"
      :image="recipe.image"
      :name="recipe.name"
      :ingredients="recipe.ingredients"
      :instructions="recipe.instructions"
      @add-likes="addLikes"
    />
  </b-container>
</template>

<script>
import Recipe from "../components/Recipe.vue";

export default {
  name: "Home",
  components: {
    Recipe
  },
  data() {
    return {
      restaurantName: "TASTY",
      totalLikes: 0,
      recipes: []
    };
  },
  methods: {
    async setRecipesAsync() {
      // async / await
      const response = await fetch("recipes.json");
      const recipes = await response.json();
      this.recipes = recipes;
    },
    setRecipes() {
      // Promise
      fetch("recipes.json")
        .then(response => {
          return response.json();
        })
        .then(recipes => {
          this.recipes = recipes;
        });
    },

    addLikes(likes) {
      this.totalLikes = likes;
    }
  },
  mounted() {
    this.setRecipesAsync();
  }
};
</script>

<style></style>
