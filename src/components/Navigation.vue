<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "Navigation"
};
</script>

<style lang="scss">
#nav {
  padding: 30px;
  text-align: center;
  background-color: rgb(206, 204, 81);

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
