<template>
  <div class="about-page">
    <div class="my-info">
      <h1 class="about info">About me</h1>
      <div class="photo info"></div>
      <p class="info-text info">
        Hi, I'm Xiang. I am a frontend developer based in the Netherlands. I
        enjoy turning a simple idea into a beautiful design, to then be a
        functional application Lorem ipsum dolor sit amet consectetur
        adipisicing elit. Corporis, temporibus dignissimos fugit, ratione eaque
        consequatur quis magnam odio repellat officiis vel provident recusandae,
        autem dicta consectetur. Aliquid suscipit quo reprehenderit.
      </p>
    </div>
    <div class="skill-part">
      <img src="../assets/Css.svg" class="images" alt="" />
      <img src="../assets/Html.svg" class="images" alt="" />
      <img src="../assets/javascript.svg" class="images" alt="" />
      <img src="../assets/vue.svg" class="images" alt="" />
      <img src="../assets/github.svg" class="images" alt="" />
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
        info.style.transform = "translateX(0px)";
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
  transition: all ease 0.3s;
}
.about-page {
  width: 60%;
  margin-top: 10vh;
  padding: 1rem;
  display: flex;
  flex-wrap: wrap;
}

.my-info {
  width: 70%;
  padding: 1rem;
}

.info:not(:last-child) {
  margin-bottom: 2rem;
}

.skill-part {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 30%;
  /* background-color: #000; */
}
.skill-part > * {
  margin-bottom: 1rem;
}

.photo {
  width: 12.5rem;
  height: 12.5rem;
  border-radius: 4px;
  background-image: url("../assets/profile.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.photo:hover {
  filter: none;
}
.about {
  color: #2c3e50;
}
.info-text {
  text-align: left;
  font-weight: 500;
  letter-spacing: 0.3px;
  line-height: 1.5rem;
}

.info {
  opacity: 0;
  transform: translateX(3.125rem);
}

.skill-part img {
  width: 1.5rem;
  height: 1.5rem;
  display: block;
  opacity: 0;
  transform: scale(0.8);
}

@media (max-width: 414px) {
  .about-page {
    width: 80%;
    /* margin-top: 10vh; */
  }
}
</style>
