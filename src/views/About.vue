<template>
  <div class="about-page">
    <div class="my-info">
      <h1 class="about info">About me</h1>
      <div class="photo info"></div>
      <p class="info-text info">
        I am a frontend developer based in the Netherlands. I enjoy turning a
        simple idea into a beautiful design, to then be a functional application
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis,
        temporibus dignissimos fugit, ratione eaque consequatur quis magnam odio
        repellat officiis vel provident recusandae, autem dicta consectetur.
        Aliquid suscipit quo reprehenderit.
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
  /* height: 80%; */
  /* display: flex;
  justify-content: space-around;
  align-items: center; */
  /* background-color: green; */
  display: flex;
  grid-template-columns: 2fr 1fr;
  padding: 1rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.089);
  border-left: 1px solid rgba(255, 255, 255, 0.089);
}

.my-info {
  width: 70%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  /* background-color: white; */
  padding: 1rem;
}

.my-info > * {
  margin-bottom: 2rem;
}

.skill-part {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: 56px;
  /* background-color: #000; */
  width: 30%;
}
.skill-part > * {
  margin-bottom: 1rem;
}

.photo {
  width: 200px;
  height: 200px;
  /* border-radius: 100%; */
  background-image: url("../assets/profile.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.about {
  color: #2c3e50;
}
.info-text {
  text-align: left;
  font-weight: 600;
  color: #344a5f;
  user-select: none;
}

.info {
  opacity: 0;
  transform: translateX(50px);
}

.skill-part img {
  width: 30px;
  height: 40px;
  display: block;
  opacity: 0;
  transform: scale(0.5);
}
</style>
