<template>
  <div id="app">
    <nav-page v-if="!'NotFound'.includes($route.name)" />
    <!-- <nav-page v-if="!$route.meta.hideNav" /> -->
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
  /* background: #2c3e50;
  background: -webkit-linear-gradient(to left, #4ca1af, #2c3e50);
  background: linear-gradient(to left, #4ca1af, #2c3e50); */
  /* background-image: linear-gradient(-60deg, #ff5858 0%, #f09819 100%); */
  /* background: #56ab2f;
  background: -webkit-linear-gradient(to right, #a8e063, #56ab2f);
  background: linear-gradient(
    to right,
    #a8e063,
    #56ab2f 
  );*/
}

#app {
  font-family: "Poppins", sans-serif;
  /* -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
  text-align: center;
  color: #2c3e50;
}
</style>
