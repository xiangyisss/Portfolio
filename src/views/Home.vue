<template>
  <div class="home">
    <div class="intro">
      <p class="text">Hello, I'm <span>Xiang.</span></p>
      <div class="gradient-text">Front-End Developer p</div>
    </div>
    <!-- <div class="profile-image"></div> -->
  </div>
</template>

<script>
export default {
  name: "Home",
  mounted() {
    // let introText = document.getElementsByClassName("gradient-text");
    // console.log(introText.innnerHTML.length);
    // introText.forEach((el, index) => {
    //   setTimeout(() => {
    //     el.classList.add("intro-style");
    //   }, index * 200);
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
  display: flex;
  justify-content: space-between;
}

.intro {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 1rem;
}

.text,
.gradient-text {
  font-size: 3rem;
  font-weight: bold;
  /* margin-bottom: 2.5rem; */
  letter-spacing: 0.05rem;
  user-select: none;
}
p span {
  color: antiquewhite;
}

.profile-image {
  background-image: url("../assets/profile-1.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  /* filter: blur(1px); */
  width: 300px;
  height: 300px;
  border-radius: 50%;
}

.gradient-text {
  opacity: 0;
}
.intro-style {
  opacity: 1;
  transition: all 1s ease;
}

/* .gradient-text {
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
