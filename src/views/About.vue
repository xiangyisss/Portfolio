<template>
  <div class="about">
    <div class="my-info">
      <div class="photo info"></div>
      <h2 class="name info">XiangYi Sun</h2>
      <p class="info-text info">
        I am a frontend developer based in the Netherlands. I enjoy turning a
        simple idea into a beautiful design, to then be a functional application
      </p>
    </div>
    <div class="skill-part">
      <img src="../assets/Css.svg" class="images" alt="" />
      <img src="../assets/Html.svg" class="images" alt="" />
      <img src="../assets/javascript.svg" class="images" alt="" />
      <img src="../assets/vue.svg" class="images" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  mounted() {
    let information = document.querySelectorAll(".info");
    let images = document.querySelectorAll(".images");
    let delay = 0;
    setTimeout(() => {
      information.forEach((info) => {
        delay += 0.1;
        info.style.opacity = "1";
        info.style.transform = "translateX(-20px)";
        info.style.transitionDelay = delay + "s";
      });

      images.forEach((image) => {
        delay += 0.1;
        image.style.opacity = "1";
        image.style.transform = "scale(1)";
        image.style.transitionDelay = delay + "s";
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
  /* height: 80%; */
  /* display: flex;
  justify-content: space-around;
  align-items: center; */
  /* background-color: green; */
  display: grid;
  grid-template-columns: 2fr 1fr;
}

.my-info {
  /* width: 100%; */
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.my-info > * {
  margin-bottom: 2rem;
}

.skill-part {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: 56px;
}
.skill-part > * {
  margin-bottom: 1rem;
}

.photo {
  width: 200px;
  height: 200px;
  border-radius: 100%;
  background-image: url("../assets/profile.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.info-text {
  text-align: left;
  font-weight: 600;
  color: #47596d;
  user-select: none;
}

.info {
  opacity: 0;
  transform: translateX(20px);
}

.skill-part img {
  width: 30px;
  height: 40px;
  display: block;
  opacity: 0;
  transform: scale(0.5);
}
</style>
