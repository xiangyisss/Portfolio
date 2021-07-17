<template>
  <nav id="nav">
    <logo ref="move" />
    <div class="nav-menu">
      <router-link :to="{ name: 'Home' }" class="nav-items" @click="moveLogo">
        Home</router-link
      >

      <router-link
        :to="{ name: 'Projects' }"
        class="nav-items"
        @click="moveLogo"
        >Projects</router-link
      >

      <router-link :to="{ name: 'About' }" class="nav-items" @click="moveLogo"
        >About</router-link
      >

      <router-link :to="{ name: 'Contact' }" class="nav-items" @click="moveLogo"
        >Contact</router-link
      >
    </div>

    <wave />
  </nav>
</template>

<script>
import Logo from "./Logo.vue";
import Wave from "@/components/Wave.vue";
export default {
  components: { Logo, Wave },
  name: "NavigationPage",
  methods: {
    moveLogo() {
      this.$refs.move.moveBox(4, 2);
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
}

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

.nav-menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 30%;
}

.nav-items {
  width: 5rem;
  height: 2.5rem;
  /* line-height: 2.5rem; */
  font-weight: 500;
  color: #2c3e50;
  display: flex;
  justify-content: start;
  align-items: center;
  position: relative;
  /* background-color: coral; */
  /* padding-left: 0.75rem; */
}

.nav-items:hover {
  /* border: 1px solid rebeccapurple;
  background-color: transparent; */
  color: #44a7c3;
  padding-left: 0.25rem;
  transition: all 0.3s;
}

.active-menu::after {
  /* border-bottom: 2px solid salmon; */
  content: "";
  width: 20px;
  height: 2px;
  background-color: #44a7c3;
  position: absolute;
  bottom: 2px;
  left: 0;
}
</style>
