<template>
  <div class="home">
    <div class="intro">
      <h1>Front-End Developer</h1>
      <p class="text">
        Experienced frontend developer with solture on HTML CSS JS and Vuejs.
        Always up for a challenge and eager to turn an idea into a working
        system or application
      </p>
      <h3>X.Sun</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  mounted() {
    // let introText = document.getElementById("delay-text");
    // let text = "Front-End Developer".split("");
    // text.forEach((el, index) => {
    //   setTimeout(() => {
    //     let span = document.createElement("span");
    //     span.innerHTML = el;
    //     introText.appendChild(span);
    //     introText.classList.add("gradient-text");
    //   }, 80 * index++);
    // });
    // introText.appendChild(span).style.opacity = "0.5";
    // introText.classList.add("delay");
    // introContent.split("").forEach((el, index) => {
    //   setTimeout(() => {
    //     el.classList.add("intro-style");
    //   }, index * 2000);
    // });
  },
};
</script>

<style scoped>
.home {
  width: 60%;
  height: 80%;

  display: flex;
  justify-content: center;
  align-items: center;
}

.intro > * {
  margin-bottom: 1rem;
}
h3 {
  text-align: right;
}
/* .intro {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 1rem;
} */

/* .delay {
  font-size: 2rem;
} */
/* 
.gradient-text {
  background-color: #ca4246;
  background-image: linear-gradient(
    45deg,
    #ca4246,
    #e16541,
    #e16541,
    #f18f43,
    #f18f43,
    #8b9862,
    #8b9862,
    #476098,
    #476098,
    #a7489b
  );
  background-size: 100%;
  background-repeat: repeat;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: rainbow-effect-rev 0.8s ease forwards;
}

.gradient-text:hover {
  animation: rainbow-effect 0.5s ease-in forwards;
}

@keyframes rainbow-effect-rev {
  0% {
    background-size: 650%;
  }
  40% {
    background-size: 650%;
  }
  100% {
    background-size: 100%;
  }
}

@keyframes rainbow-effect {
  0% {
    background-size: 100%;
  }
  80% {
    background-size: 650%;
  }
  100% {
    background-size: 650%;
  }
} */
</style>
