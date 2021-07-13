<template>
  <div class="home">
    <h1 class="item">Front-End Developer</h1>
    <p class="item">
      Experienced frontend developer with solture on HTML CSS JS and Vuejs.
      Always up for a challenge and eager to turn an idea into a working system
      or application
    </p>
    <h3 class="item">X.Sun</h3>
  </div>
</template>

<script>
export default {
  name: "Home",
  mounted() {
    let items = document.querySelectorAll(".item");
    let delay = 0;
    setTimeout(() => {
      items.forEach((item) => {
        delay += 0.1;
        item.style.opacity = 1;
        item.style.transform = "translate(0px, 0px)";
        // item.style.transform = "translateX(0px)";
        item.style.transitionDelay = delay + "s";
      });
    }, 0);
  },
};
</script>

<style scoped>
* {
  transition: all ease-in-out 0.4s;
}
.home {
  width: 60%;
  /* height: 80%; */
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* background-color: yellow; */
  padding: 1rem;
}

.home > * {
  margin-bottom: 2.5rem;
}

h1,
p,
h3 {
  opacity: 0;
  transform: translate(50px, 50px);
}
h3 {
  text-align: right;
}
p {
  user-select: none;
}
</style>
