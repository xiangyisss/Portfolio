<template>
  <div class="projects">
    <div class="work project-1"></div>
    <div class="work project-2"></div>
    <div class="work project-3"></div>
  </div>
</template>

<script>
export default {};
</script>
<style scoped>
.projects {
  display: flex;
  width: 60%;
  height: 80%;
  justify-content: center;
  align-items: center;
  /* background-color: black; */
}
.work {
  width: 100px;
  height: 200px;
  border: 2px solid steelblue;
  border-radius: 16px 0px 16px 0px;
  margin: 20px;
  cursor: pointer;
}
.work:hover {
  transform: scale(1.2);
  transition: 0.5s ease-in;
}
</style>
