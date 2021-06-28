<template>
  <div class="about">
    <div class="my-info">
      <div class="photo"></div>
      <h3 class="name">XiangYi Sun</h3>
      <p class="info-text">
        I am a frontend developer from China based in the Netherlands. I enjoy
        turning a simple idea into a beautiful design, to then be a functional
        application
      </p>
    </div>
    <div class="skill-part">
      <img src="../assets/css-3.svg" alt="" />
      <img src="../assets/css-3.svg" alt="" />
      <img src="../assets/css-3.svg" alt="" />
      <img src="../assets/css-3.svg" alt="" />
    </div>
  </div>
</template>

<style scoped>
.about {
  width: 60%;
  display: flex;
  justify-content: space-between;
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

.skill-part img {
  width: 30px;
  height: 40px;
  display: block;
}
</style>
