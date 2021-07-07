<template>
  <nav id="nav">
    <div class="logo">
      <div class="big-square">
        <div class="square square-1"></div>
        <div class="square square-2"></div>
      </div>
      <div class="square square-3"></div>
    </div>
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
      <div class="line line1"></div>
      <div class="line line2"></div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavigationPage",
  methods: {
    moveLogo() {
      // let buttons = document.querySelectorAll(".nav-items");

      // buttons.forEach((item) => {
      //   item.addEventListener("click", () => {
      //     moveSquares(85, 5);
      //   });
      // });

      let square1 = document.querySelector(".square-1");
      let square2 = document.querySelector(".square-2");
      let square3 = document.querySelector(".square-3");
      square1.style.transform = "translateY(-15px)  rotate(45deg)";
      square2.style.transform = "translateY(15px)  rotate(45deg)";
      square3.style.transform = "translateX(5px)  rotate(45deg)";

      setTimeout(() => {
        square1.style.transform = "translateY(-10px)  rotate(45deg)";
        square2.style.transform = "translateY(10px) rotate(45deg)";
        square3.style.transform = "translateX(0px)  rotate(45deg)";
      }, 300);
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

.logo {
  width: 18.75rem;
  height: 18.75rem;
  border-radius: 100%;
  margin-left: -140px;
  margin-right: 100px;
  background: linear-gradient(193.13deg, #88a0f4 7.05%, #4560be 87.55%);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
  display: flex;
  justify-content: center;
  align-items: center;
  padding-left: 40px;
}

.big-square {
  position: relative;
}

.square-1,
.square-2 {
  width: 7.5rem;
  height: 7.5rem;
  background-color: rgb(246, 246, 248);
  transform: rotate(45deg);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
}

.square-1 {
  transform: translateY(-10px) rotate(45deg);
}

.square-2 {
  transform: translateY(10px) rotate(45deg);
}

.square-3 {
  width: 5rem;
  height: 5rem;
  background-color: rgb(246, 246, 248);
  transform: rotate(45deg);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
}

.nav-items {
  width: 6rem;
  height: 2rem;
  background-color: rgb(185, 175, 194);
  border-radius: 4px;
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

.line1 {
  position: absolute;
  width: 100vw;
  height: 650px;
  background: linear-gradient(
    143.65deg,
    #88a0f4 20.14%,
    rgba(136, 160, 244, 0) 51.8%
  );
  left: 100%;
  top: 80%;
  transform: rotate(-15deg);
}
.line2 {
  position: absolute;
  width: 100vw;
  height: 650px;
  background: linear-gradient(
    143.65deg,
    #88a0f4 20.14%,
    rgba(136, 160, 244, 0) 51.8%
  );
  left: 120%;
  top: 70%;
  transform: rotate(-25deg);
}
</style>
