<template>
  <div class="app">
    <!-- <nav-page v-if="!'NotFound'.includes($route.name)" /> -->
    <!-- <nav-page v-if="!$route.meta.hideNav" /> -->
    <div>
      <nav-page />
    </div>
    <div class="pages">
      <router-view />
    </div>
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

.app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 16px;
  color: #2c3e50;
  display: flex;
  flex-direction: row;
}

.pages {
  margin-left: 30%;

  padding-left: 50px;
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: start;
  align-items: center;
  /* background-color: pink; */
}
</style>
