<template>
  <div class="home">
    <div class="intro">
      <p class="text">Hello, I'm Xiang.</p>
    </div>
    <div id="delay-text"></div>
  </div>
</template>

<script>
export default {
  name: "Home",
  mounted() {
    let introText = document.getElementById("delay-text");
    let text = "Front-End Developer".split("");
    text.forEach((el, index) => {
      setTimeout(() => {
        let span = document.createElement("span");
        span.innerHTML = el;
        introText.appendChild(span);
        introText.classList.add("gradient-text");
      }, 80 * index++);
      // introText.appendChild(span).style.opacity = "0.5";
    });
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
  position: absolute;
  /* z-index: 1; */
  width: 80%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* .intro {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 1rem;
} */

.text,
.gradient-text {
  font-size: 3rem;
  font-weight: bold;
  /* margin-bottom: 2.5rem; */
  letter-spacing: 0.05rem;
  user-select: none;
}
p span {
  color: rgb(255, 151, 15);
}

/* .delay {
  font-size: 2rem;
} */

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
}
</style>
