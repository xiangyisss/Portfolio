<template>
  <nav id="nav">
    <router-link :to="{ name: 'Home' }"
      ><li @click="changeDirection">Home</li></router-link
    >
    <router-link :to="{ name: 'Projects' }"
      ><li @click="changeDirection">Projects</li></router-link
    >
    <router-link :to="{ name: 'Contact' }"
      ><li @click="changeDirection">Contact</li></router-link
    >
    <router-link :to="{ name: 'About' }"
      ><li @click="changeDirection">About</li></router-link
    >
  </nav>
</template>

<script>
export default {
  name: "NavigationPage",
  data() {
    return {
      show: false,
    };
  },
  mounted() {
    const delayMenu = document.querySelectorAll("li");
    delayMenu.forEach((el, index) => {
      setTimeout(() => {
        el.classList.add("nav-style");
      }, index * 600);
    });
  },
  // methods: {
  //   changeDirection() {
  //     const changeXy = document.getElementById("nav");
  //     changeXy.classList.add("change-xy");
  //   },
  // },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#nav {
  height: 100vh;
  width: 100%;
  position: absolute;
}

nav,
li {
  display: flex;
  justify-content: center;
  align-items: center;
}

a {
  text-decoration: none;
  color: inherit;
}

li {
  list-style: none;
  font-weight: bold;
  width: 5rem;
  height: 5rem;
  margin: 1rem;
  border-radius: 50%;
  background: white;
  color: #576777;
  opacity: 0;
  user-select: none;
}

li:hover {
  background: #576777;
  color: rgb(231, 222, 222);
  transition: all 0.5s;
}

.nav-style {
  opacity: 1;
  background: rgb(140, 226, 226);
  transform: rotate(1turn);
  margin: 2.5rem;
  transition: all 0.8s ease;
}

/* .change-xy {
  display: flex;
  flex-direction: column;
} */
</style>
