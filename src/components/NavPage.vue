<template>
  <nav id="nav">
    <div class="logo">
      <router-link :to="{ name: 'Home' }"
        ><li class="home" @click="changeDirection">Logo</li></router-link
      >
    </div>
    <div class="nav-item">
      <router-link :to="{ name: 'Projects' }"
        ><li class="project" @click="changeDirection">Projects</li></router-link
      >
      <router-link :to="{ name: 'Contact' }"
        ><li class="contact" @click="changeDirection">Contact</li></router-link
      >
      <router-link :to="{ name: 'About' }"
        ><li class="about" @click="changeDirection">About</li></router-link
      >
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavigationPage",

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
  //     // this.$router.push(this.$router.currentRoute);
  //   },
  // },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#nav {
  height: 20%;
  width: 80%;
  margin: auto;
  display: flex;
  justify-content: space-between;
}

.nav-item,
.logo {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* nav,
li {
  display: flex;
  justify-content: center;
  align-items: center;
} */

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

/* .home {
  position: absolute;
  top: 0;
  left: 0;
}

.project {
  position: absolute;
  top: 0;
  right: 0;
}

.contact {
  position: absolute;
  bottom: 0;
  left: 0;
}

.about {
  position: absolute;
  bottom: 0;
  right: 0;
} */

li {
  list-style: none;
  font-weight: bold;

  /*
  background: white; */
  color: #576777;
  /* opacity: 0; */
  /* user-select: none; */
}

li:hover {
  /* background: #576777; */
  color: rgb(231, 222, 222);
  transition: all 0.5s;
}

.nav-style {
  opacity: 1;
  transform: rotate(1turn);
  transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
}

/* .change-xy {
  flex-direction: column;
  align-items: flex-end;
transform: rotate(1turn);
  transition: all 0.5s ease;
}*/
</style>
