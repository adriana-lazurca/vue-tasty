<template>
  <b-row class="mt-5">
    <b-col cols="6" class="recipe-item">
      <img class="recipe-item__image rounded-pill" :src="image.source" :alt="image.alt" />
    </b-col>
    <b-col cols="5">
      <h4>{{ name }}</h4>
      <p>Ingredients:</p>
      <ul>
        <li
          v-for="(ingredient, index) in ingredients"
          :key="`ingredient-${index}`"
        >
          {{ ingredient }}
        </li>
      </ul>
      <div>
        <b-button size="sm" @click="toggle">
          {{ show ? "Hide" : "Show" }} Instructions
        </b-button>
        <b-alert v-model="show" class="mt-3" dismissible>
          {{ instructions }}
        </b-alert>
      </div>
    </b-col>
    <b-col cols="1">
      <!-- <b-button class="btn btn-outline" :click="counter += 1"><b-icon class="h6 mb-0" icon="heart-fill"></b-icon></b-button> -->
      <button @click="updateLikes(likesNr)"><b-icon class="h5 mb-0" icon="heart-fill"></b-icon></button>
      <p class="font-weight-light">{{likesNr}} likes</p>
    </b-col>
  </b-row>
</template>

<script>
export default {
  name: "Recipe",

  props: {
    image: {
      type: Object,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    ingredients: {
      type: Array,
      required: true
    },
    instructions: {
      type: String,
      required: true
    }
  },

  data() {
    return {
      show: false,
      likesNr: 0
    };
  },

  methods: {
    toggle() {
      this.show = !this.show;
    },
    updateLikes(likesNr){
       this.likesNr++;
       this.$emit("add-likes", likesNr);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.recipe-item {
  //width: 50%;
  // text-align: center;
  //display: flex;
}

.recipe-item__image {
  max-width: 80%;
}

ul {
  list-style-type: none;
}
</style>
