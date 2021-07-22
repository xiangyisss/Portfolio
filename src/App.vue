<template>
  <div class="app">
    <!-- <nav-page v-if="!'NotFound'.includes($route.name)" /> -->
    <!-- <nav-page v-if="!$route.meta.hideNav" /> -->
    <div>
      <nav-page v-if="width > 600" />
      <!-- <nav-page v-if="!'NotFound'.includes($route.name)" /> -->
      <!-- <nav-page /> -->
      <mobile-nav-page v-if="width < 600" />
    </div>
    <div class="pages">
      <router-view />
    </div>
  </div>
</template>

<script>
import NavPage from "@/components/NavPage.vue";
import MobileNavPage from "./components/MobileNavPage.vue";

export default {
  components: { NavPage, MobileNavPage },
  data() {
    return {
      width: 0,
    };
  },
  created() {
    this.width = window.innerWidth;
    window.addEventListener("resize", this.checkWidth);
  },

  methods: {
    checkWidth() {
      this.width = window.innerWidth;
    },
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
}

.pages {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
