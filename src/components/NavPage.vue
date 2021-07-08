<template>
  <nav id="nav">
    <logo ref="move" />
    <div class="nav-menu">
      <router-link :to="{ name: 'Home' }"
        ><div class="nav-items" @click="moveLogo">Home</div></router-link
      >
      <router-link :to="{ name: 'About' }"
        ><div class="nav-items" @click="moveLogo">About</div></router-link
      >
      <router-link :to="{ name: 'Projects' }"
        ><div class="nav-items" @click="moveLogo">Projects</div></router-link
      >
      <router-link :to="{ name: 'Contact' }"
        ><div class="nav-items" @click="moveLogo">Contact</div></router-link
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
      this.$refs.move.moveLogo(15, 5);
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
  width: 30%;
  display: flex;
  justify-content: start;
  align-items: center;
}

.nav-items {
  width: 4rem;
  height: 2rem;
  border-bottom: 1px solid blue;

  color: #262831;
  text-align: left;
  display: grid;
  place-items: center;
}

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

.nav-items:hover {
  border: 1px solid rebeccapurple;
  background-color: transparent;
  color: #576777;
  transition: all 0.5s;
}

.wave {
  height: 5%;
  width: 100vw;
  position: absolute;
  bottom: 0;
  left: 130%;
  transform: rotate(-25deg);
  background: #015871;
}

.line {
  background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/85486/wave.svg)
    repeat-x;
  position: absolute;
  top: -185px;
  width: 5000px;
  height: 187px;
  animation: wave 7s cubic-bezier(0.16, 1.11, 0.73, 0.18) infinite;
  transform: rotate3d(0, 0, 0);
}

.line:nth-of-type(2) {
  top: -175px;
  animation: wave 7s cubic-bezier(0.16, 1.11, 0.73, 0.18) -0.125s infinite,
    swell 7s ease -1.25s infinite;
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
    transform: translate3d(0, -25px, 0);
  }
  50% {
    transform: translate3d(0, 5px, 0);
  }
}
</style>
