<template>
  <nav id="nav">
    <logo ref="move" />
    <div class="nav_menu">
      <router-link :to="{ name: 'Home' }" class="nav_items" @click="moveLogo">
        Home</router-link
      >
      <router-link :to="{ name: 'About' }" class="nav_items" @click="moveLogo"
        >About</router-link
      >

      <router-link
        :to="{ name: 'Projects' }"
        class="nav_items"
        @click="moveLogo"
        >Projects</router-link
      >

      <router-link :to="{ name: 'Contact' }" class="nav_items" @click="moveLogo"
        >Contact</router-link
      >
    </div>

    <wave v-if="width > 700" />
  </nav>
</template>

<script>
import Logo from "./Logo.vue";
import Wave from "@/components/Wave.vue";
export default {
  components: { Logo, Wave },
  name: "NavigationPage",
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
    moveLogo() {
      this.$refs.move.moveBox(2, 2);
    },
    checkWidth() {
      this.width = window.innerWidth;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  transition: all ease-in-out 0.3s;
}
#nav {
  position: fixed;
  height: 10vh;
  width: 100%;
  margin: 0 auto;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 1rem;
  z-index: 1;
}

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

.nav_menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 30%;
  height: 10vh;
  margin-right: 18rem;
}

.nav_items {
  width: 5rem;
  height: 2.5rem;
  font-weight: 500;
  color: #2c3e50;
  display: flex;
  justify-content: start;
  align-items: center;
  position: relative;
}

.nav_items:hover {
  color: #44a7c3;
  padding-left: 0.25rem;
  transition: all 0.3s;
}

.active_menu::after {
  content: "";
  width: 1.25rem;
  height: 0.125rem;
  background-color: #44a7c3;
  position: absolute;
  bottom: 0.125rem;
  left: 0;
}
</style>
