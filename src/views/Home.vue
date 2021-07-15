<template>
  <div class="home">
    <h1 class="item name">XiangYi Sun.</h1>
    <h2 class="item front-end">Front-End Developer</h2>
    <p class="item describ">
      Experienced frontend developer with solture on HTML CSS JS and Vuejs.
      Always up for a challenge and eager to turn an idea into a working system
      or application.
    </p>

    <router-link :to="{ name: 'Contact' }">
      <h3 class="item contact">Contact me</h3>
    </router-link>
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

.item:not(.describ) {
  margin-bottom: 0.75rem;
}

.name {
  font-size: 60px;
  font-weight: 800;
}
.front-end {
  font-size: 58px;
  color: #344a5f;
  font-weight: 700;
}
.describ {
  font-size: 18px;
  font-weight: 500;
  color: #344a5f;
  margin: 1rem 0 3rem 0;
}

a {
  text-decoration: none;
  color: inherit;
  width: 140px;
  height: 50px;
}

.contact {
  width: 140px;
  height: 50px;
  text-align: center;
  border: 2px solid #44cfcb;
  color: #44cfcb;
  border-radius: 4px;
  background-color: trasparent;
  line-height: 50px;
}

.item {
  opacity: 0;
  transform: translate(50px, 50px);
  user-select: none;
}
</style>
