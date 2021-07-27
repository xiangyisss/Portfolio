<template>
  <div class="app">
    <!-- <nav-page v-if="!'NotFound'.includes($route.name)" /> -->
    <!-- <nav-page v-if="!$route.meta.hideNav" /> -->
    <!-- <div class="landing">
      <landing-page />
    </div> -->
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
// import LandingPage from "@/components/LandingPage.vue";

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
  // mounted() {
  //   let landingPage = document.querySelector(".landing");
  //   setTimeout(() => {
  //     landingPage.classList.toggle("close");
  //   }, 1800);
  // },
  methods: {
    checkWidth() {
      this.width = window.innerWidth;
    },
  },
};
</script>

<style>
.landing {
  width: 100%;
  height: 100vh;
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  position: fixed;
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2 ease-in;
}
.close {
  visibility: hidden;
  opacity: 0;
  transition: all 0.5s ease-in-out;
}
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
