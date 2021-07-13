<template>
  <nav id="nav">
    <logo ref="move" />
    <div class="nav-menu">
      <router-link :to="{ name: 'Home' }" class="nav-items" @click="moveLogo">
        Home</router-link
      >
      <router-link :to="{ name: 'About' }" class="nav-items" @click="moveLogo"
        >About</router-link
      >
      <router-link
        :to="{ name: 'Projects' }"
        class="nav-items"
        @click="moveLogo"
        >Projects</router-link
      >
      <router-link :to="{ name: 'Contact' }" class="nav-items" @click="moveLogo"
        >Contact</router-link
      >
    </div>

    <div class="wave">
      <div class="line"></div>
      <div class="line"></div>
    </div>
  </nav>
</template>

<script>
import Logo from "./Logo.vue";
export default {
  components: { Logo },
  name: "NavigationPage",
  methods: {
    moveLogo() {
      this.$refs.move.moveBox(15, 5);
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
  height: 100vh;
  max-width: 30%;
  display: flex;
  justify-content: start;
  align-items: center;
  /* background-color: coral; */
}

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

.nav-items {
  width: 5rem;
  height: 2.5rem;
  /* line-height: 2.5rem; */
  font-weight: 500;
  color: #262831;
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
  color: #6c7d8d;
  padding-left: 0.25rem;
  transition: all 0.3s;
}

.active-menu::after {
  /* border-bottom: 2px solid salmon; */
  content: "";
  width: 20px;
  height: 2px;
  background-color: #3994ad;
  position: absolute;
  bottom: 2px;
  left: 0;
}

.wave {
  height: 5%;
  width: 100vw;
  position: absolute;
  bottom: 0;
  left: 130%;
  transform: rotate(-28deg);
  background: #015871;
}

.line {
  background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/85486/wave.svg)
    repeat-x;
  position: absolute;
  top: -153px;
  width: 10000px;
  height: 155px;
  animation: wave 7s ease-in-out infinite;
  transform: rotate3d(0, 0, 0);
}

.line:nth-of-type(2) {
  top: -150px;
  animation: wave 7s ease-in-out infinite, swell 7s ease -1.25s infinite;
}

@keyframes wave {
  0% {
    margin-left: 0;
  }
  100% {
    margin-left: -1600px;
  }
}

@keyframes swell {
  0%,
  100% {
    transform: translate3d(0, -15px, 0);
  }
  50% {
    transform: translate3d(0, 5px, 0);
  }
}
</style>
