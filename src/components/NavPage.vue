<template>
  <nav id="nav">
    <div class="logo"></div>
    <div class="nav-menu">
      <router-link :to="{ name: 'Home' }"
        ><div class="nav-items">Home</div></router-link
      >
      <router-link :to="{ name: 'About' }"
        ><div class="nav-items">About</div></router-link
      >
      <router-link :to="{ name: 'Projects' }"
        ><div class="nav-items">Projects</div></router-link
      >
      <router-link :to="{ name: 'Contact' }"
        ><div class="nav-items">Contact</div></router-link
      >
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavigationPage",
  methods: {
    // showMenu() {
    //   this.show = !this.show;
    //   if (!this.show) {
    //     let menu = document.getElementById("nav-items");
    //     menu.style.marginTop = "0px";
    //     menu.style.opacity = "1";
    //     menu.classList.add("show-menu");
    //   }
    // },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#nav {
  position: fixed;
  height: 100vh;
  width: 30%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* background-color: black; */
}

.logo {
  width: 18.75rem;
  height: 18.75rem;
  background-color: plum;
  border-radius: 100%;
  margin-left: -120px;
  margin-right: 100px;
}

.nav-items {
  width: 6rem;
  height: 2rem;
  background-color: rgb(183, 154, 212);
  border-radius: 4px;
  color: aliceblue;
  text-align: left;
  display: grid;
  place-items: center;
}

a {
  text-decoration: none;
  color: inherit;
  margin: 1rem;
}

/* li::after {
  content: "";
  width: 4px;
  height: 2px;
  background-color: red;
} */

.nav-items:hover {
  border: 1px solid rebeccapurple;
  background-color: transparent;
  color: #576777;
  transition: all 0.5s;
}
</style>
