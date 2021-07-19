<template>
  <nav id="nav">
    <logo class="logo" />
    <div class="nav-menu">
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
};
</script>

<style scoped>
#nav {
  width: 100%;
  height: 10vh;
  position: fixed;
  z-index: 1;
  background-color: whitesmoke;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 1rem;
}
.nav-menu {
  width: 70%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

a {
  text-decoration: none;
  font-weight: 500;
  color: #2c3e50;
  font-size: 0.75rem;
}
</style>
