<template>
  <div id="app">
    <nav-page />
    <router-view />
  </div>
</template>

<script>
import NavPage from "@/components/NavPage.vue";

export default {
  components: { NavPage },
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
html,
body {
  /* width: 100%; */
  height: 100vh;
  background: #2c3e50; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to left,
    #4ca1af,
    #2c3e50
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to left,
    #4ca1af,
    #2c3e50
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
  text-align: center;
  color: #2c3e50;
}
</style>
