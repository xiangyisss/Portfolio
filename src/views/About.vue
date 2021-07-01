<template>
  <div class="about">
    <div class="my-info">
      <div class="photo info"></div>
      <h3 class="name info">XiangYi Sun</h3>
      <p class="info-text info">
        I am a frontend developer from China based in the Netherlands. I enjoy
        turning a simple idea into a beautiful design, to then be a functional
        application
      </p>
    </div>
    <div class="skill-part">
      <img src="../assets/css-3.svg" class="images" alt="" />
      <img src="../assets/css-3.svg" class="images" alt="" />
      <img src="../assets/css-3.svg" class="images" alt="" />
      <img src="../assets/css-3.svg" class="images" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  mounted() {
    let information = document.querySelectorAll(".info");
    let delay = 0;
    setTimeout(() => {
      information.forEach((info) => {
        delay += 0.1;
        info.style.opacity = "1";
        info.style.transform = "translateX(-40px)";
        info.style.transform = "translateY(-40px)";
        info.style.transitionDelay = delay + "s";
      });
    }, 0);
  },
};
</script>

<style scoped>
* {
  transition: all ease 0.4s;
}
.about {
  width: 60%;
  height: 80%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.my-info {
  width: 70%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.my-info > *,
.skill-part > * {
  margin-bottom: 1rem;
}

.photo {
  width: 200px;
  height: 200px;
  border-radius: 100%;
  background-image: url("../assets/profile-1.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.info-text {
  padding: 8px;
}

.info {
  opacity: 0;
  transform: translateX(40px);
  transform: translateY(40px);
}

.skill-part img {
  width: 30px;
  height: 40px;
  display: block;
  opacity: 0;
  transform: translateY(-40px);
}
</style>
