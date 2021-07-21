<template>
  <div class="about-page">
    <div class="my-info">
      <h1 class="about info">About me</h1>

      <p class="info-text info">
        Hi, I'm Xiang. I am a frontend developer based in the Netherlands. I
        enjoy turning a simple idea into a beautiful design, to then be a
        functional application Lorem ipsum dolor sit amet consectetur
        adipisicing elit. Corporis, temporibus dignissimos fugit, ratione eaque
        consequatur quis magnam odio repellat officiis vel provident recusandae,
        autem dicta consectetur. Aliquid suscipit quo reprehenderit.
      </p>
      <div class="skill-part">
        <h3 class="skill_text info">Skills to focus on</h3>
        <img src="../assets/Css.svg" class="images" alt="" />
        <img src="../assets/Html.svg" class="images" alt="" />
        <img src="../assets/javascript.svg" class="images" alt="" />
        <img src="../assets/vue.svg" class="images" alt="" />
        <img src="../assets/github.svg" class="images" alt="" />
      </div>
    </div>

    <div class="my_photo">
      <div class="photo"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  mounted() {
    let information = document.querySelectorAll(".info");
    let images = document.querySelectorAll(".images");
    let photo = document.querySelector(".photo");
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
        photo.style.opacity = "1";
        photo.style.transform = "scale(1)";
        photo.style.transitionDelay = delay + "s";
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

  /* background-color: pink; */
}

.my-info {
  width: 70%;
  padding: 1rem;
  margin-bottom: 2rem;
}

.info {
  margin-bottom: 2rem;
  opacity: 0;
  transform: translateX(3.125rem);
}

.my_photo {
  width: 30%;
  /* padding: 1rem; */
  display: flex;
  justify-content: flex-end;
  align-items: center;

  /* background-color: #fff; */
}
.photo {
  width: 10rem;
  height: 10rem;
  border-radius: 4px;
  background-image: url("../assets/profile.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  opacity: 0;
  transform: scale(0.8);
}

.info-text {
  text-align: left;
  font-weight: 500;
  letter-spacing: 0.3px;
  line-height: 1.5rem;
}

/* .info {
  opacity: 0;
  transform: translateX(3.125rem);
} */

.skill_text {
  margin-bottom: 0.75rem;
}

img {
  width: 1.5rem;
  height: 1.5rem;
  margin-right: 0.75rem;
  opacity: 0;
  transform: scale(0.8);
}

@media (max-width: 600px) {
  .about-page {
    width: 90%;
    display: block;
  }
  .my-info {
    width: 100%;
  }
  .my_photo {
    width: 100%;
    justify-content: center;
  }
}
</style>
