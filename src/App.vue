<template>
  <div class="app">
    <!-- <nav-page v-if="!'NotFound'.includes($route.name)" /> -->
    <!-- <nav-page v-if="!$route.meta.hideNav" /> -->
    <div>
      <nav-page v-if="windowWidth > 600" />
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
  data() {
    return {
      windowWidth: window.innerWidth,
    };
  },
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
  background: white;
  /* background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%); */
  /* user-select: none; */
  /* display: flex;
  flex-direction: row; */
}

.pages {
  /* margin-left: 20%;
  padding-left: 50px; */
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
