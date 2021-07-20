<template>
  <nav id="nav">
    <logo class="logo" />
    <div class="open-menu-button" @click="openMenu">
      <div class="strick"></div>
      <div class="strick"></div>
      <div class="strick"></div>
    </div>
    <div class="overlay"></div>
    <div class="nav-menu">
      <!-- <div class="close-menu-button">
        <div class="line line-1"></div>
        <div class="line line-2"></div>
      </div> -->
      <router-link :to="{ name: 'Home' }" class="nav-items"> Home</router-link>
      <router-link :to="{ name: 'About' }" class="nav-items">About</router-link>

      <router-link :to="{ name: 'Projects' }" class="nav-items"
        >Projects</router-link
      >

      <router-link :to="{ name: 'Contact' }" class="nav-items"
        >Contact</router-link
      >
    </div>
  </nav>
</template>

<script>
import Logo from "./Logo.vue";
export default {
  name: "MobileNavPage",
  components: {
    Logo,
  },
  methods: {
    openMenu() {
      let menu = document.querySelector(".nav-menu");
      let overlay = document.querySelector(".overlay");
      menu.classList.toggle("open");
      if (menu.classList.contains("open")) {
        overlay.style.opacity = 1;
      } else {
        overlay.style.opacity = 0;
      }
    },
  },
};
</script>

<style scoped>
#nav {
  width: 100%;
  height: 10vh;
  position: fixed;
  z-index: 1;
  /* background-color: whitesmoke; */
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

.overlay {
  width: 100%;
  height: 90vh;
  position: fixed;
  top: 10vh;
  left: 0;
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(2px);
  opacity: 0;
  transition: opacity 0.2s ease-in;
}

.nav-menu {
  width: 50%;
  height: 90vh;
  margin-top: 10vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  /* background: #fff; */
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  position: fixed;
  top: 0;
  right: 0;
  transform: translateX(100%);
  transition: all 0.2s ease-in;
}

.open {
  transform: translateX(0%);
}

.menu-open .nave-menu {
  /* transform: translateX(0); */
  background-color: pink;
}

.nav-items {
  margin: 2rem;
}

a {
  text-decoration: none;
  font-weight: 500;
  color: #2c3e50;
  font-size: 0.75rem;
}

.open-menu-button {
  width: 50px;
  height: 50px;
  /* background-color: black; */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.strick {
  width: 28px;
  height: 2px;
  background-color: #fff;
  border-radius: 8px;
}

.strick:not(:last-child) {
  margin-bottom: 0.5rem;
}
/* .close-menu-button {
  width: 50px;
  height: 50px;
  margin: 0.75rem 0 3rem 0;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
} */

.line {
  width: 30px;
  height: 3px;
  background-color: #2c3e50;
  border-radius: 4px;
  position: absolute;
  top: 50%;
  transform: translate(-50%, 0);
}
.line-1 {
  transform: rotate(45deg);
}
.line-2 {
  transform: rotate(-45deg);
}
</style>
