<template>
  <nav id="nav">
    <logo class="logo" />
    <div class="nav_button" @click="openMenu">
      <div class="burger_btn"></div>
    </div>
    <div class="overlay" @click="closeMenu"></div>
    <div class="nav_menu">
      <router-link :to="{ name: 'Home' }" class="nav_items" @click="closeMenu">
        Home</router-link
      >
      <router-link :to="{ name: 'About' }" class="nav_items" @click="closeMenu"
        >About</router-link
      >

      <router-link
        :to="{ name: 'Projects' }"
        class="nav_items"
        @click="closeMenu"
        >Projects</router-link
      >

      <router-link
        :to="{ name: 'Contact' }"
        class="nav_items"
        @click="closeMenu"
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
      this.burgerBtn();
      let menu = document.querySelector(".nav_menu");
      let overlay = document.querySelector(".overlay");
      menu.classList.toggle("open");
      if (menu.classList.contains("open")) {
        overlay.style.opacity = 1;
        overlay.style.visibility = "visible";
      } else {
        overlay.style.opacity = 0;
        overlay.style.visibility = "hidden";
      }
    },

    burgerBtn() {
      let btn = document.querySelector(".nav_button");
      btn.classList.toggle("burger_btn_open");
    },

    closeMenu() {
      this.burgerBtn();
      let menu = document.querySelector(".nav_menu");
      let overlay = document.querySelector(".overlay");
      menu.classList.remove("open");
      overlay.style.opacity = 0;
      overlay.style.visibility = "hidden";
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
  /* background: linear-gradient(193.13deg, #88a0f4 7.05%, #4560be 87.55%); */
  background-color: #4560be;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

.overlay {
  width: 100%;
  height: 90vh;
  margin-top: 10vh;
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgba(227, 229, 236, 0.5);
  backdrop-filter: blur(1px);
  opacity: 0;
  visibility: hidden;

  transition: opacity 0.2s ease-in;
  transition: all 0.3s ease-in-out;
}

.nav_menu {
  width: 50%;
  height: 90vh;
  margin-top: 10vh;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  background: linear-gradient(293.13deg, #88a0f4 7.05%, #4560be 87.55%);
  position: fixed;
  top: 0;
  right: 0;
  transform: translate(100%);
  transition: all 0.2s ease-in;
}

.open {
  transform: translate(0%);
  /* width: 100%; */
}

.nav_items {
  margin: 1.5rem;
  width: 100%;
  height: 50px;
  display: grid;
  place-items: center;
}

a {
  text-decoration: none;
  font-weight: 500;
  /* color: #2c3e50; */
  color: white;
  font-size: 1rem;
  padding: 1rem;
}

.nav_button {
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  background-color: transparent;
  /* border: 2px solid whitesmoke; */
}

.burger_btn {
  width: 30px;
  height: 4px;
  background-color: whitesmoke;
  border-radius: 4px;
  transition: all 0.3s ease-in-out;
}

.burger_btn::before,
.burger_btn::after {
  content: "";
  width: 30px;
  height: 4px;
  background-color: whitesmoke;
  border-radius: 4px;
  display: block;
  position: absolute;
  transition: all 0.3s ease-in-out;
}

.burger_btn::before {
  transform: translateY(-10px);
}
.burger_btn::after {
  transform: translateY(10px);
}

.burger_btn_open .burger_btn {
  background-color: transparent;
  transform: translateX(50px);
}
.burger_btn_open .burger_btn::before {
  transform: rotate(45deg) translate(-35px, 35px);
}
.burger_btn_open .burger_btn::after {
  transform: rotate(-45deg) translate(-35px, -35px);
}
.active_menu {
  background-color: rgba(128, 128, 128, 0.24);
}
</style>
