<template>
  <div class="recipe-item ml-5">
    <img class="recipe-item__image ml-5" :src="image.source" :alt="image.alt" />
    <h4>{{ name }}</h4>
    <ul>
    </ul>
  </div>
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
    ingredients:{
      type: Array,
      required: true
    },
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.recipe-item {
  //width: 50%;
  text-align: center;
  //display: flex;
}

.recipe-item__image {
  max-width: 50%;
}
</style>
