<template>
  <div class="home">
    <p class="text">
      I'm <span class="highlight">Xiang.</span><br />
      Front-End Developer
    </p>
  </div>
</template>

<script>
export default {
  name: "Home",
};
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  /* position: relative; */
  /* align-items: center; */
}
.text {
  font-size: 3rem;
  font-weight: bold;
  /* margin-bottom: 2.5rem; */
  letter-spacing: 0.05rem;
  user-select: none;
  position: absolute;
  top: 90px;
}
.highlight {
  color: antiquewhite;
}
</style>
