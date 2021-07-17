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
      <p class="item contact">Contact me</p>
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
  margin-top: 10vh;
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
  font-size: 3.75rem;
  font-weight: 800;
}
.front-end {
  font-size: 3.625rem;
  color: #344a5f;
  font-weight: 700;
}
.describ {
  font-size: 1rem;
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
  width: 110px;
  height: 44px;
  text-align: center;
  font-size: 1rem;
  font-weight: 500;
  border: 2px solid #44a7c3;
  color: #44a7c3;
  border-radius: 4px;
  line-height: 44px;
  position: relative;
  overflow: hidden;
}

.contact::before {
  content: " ";
  width: 110px;
  height: 44px;
  background-color: #44a8c344;
  border: none;
  position: absolute;
  z-index: -1;
  left: 0;
  top: -2px;
  border-radius: 4px;
  transform: translateX(-110px);
}

.contact:hover::before {
  transform: translateX(0%);
  transition: all 0.2s ease;
}

.item {
  opacity: 0;
  transform: translate(50px, 50px);
  user-select: none;
}
</style>
