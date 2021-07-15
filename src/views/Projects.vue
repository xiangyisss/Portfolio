<template>
  <div class="projects">
    <div class="work project-1"></div>
    <div class="work project-2"></div>
    <div class="work project-3"></div>
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
  width: 60%;

  display: grid;
  grid-template-columns: repeat(3, 1fr);
  place-items: center;
  grid-gap: 20px;
  /* background-color: black; */
  padding: 1rem;
}
.work {
  width: 200px;
  height: 200px;
  border: 2px solid steelblue;
  border-radius: 4px;
  /* margin: 20px; */
  cursor: pointer;
}

.work:first-child {
  margin-left: 0px;
}
/* .work:hover {
  transform: scale(1.2);
  transition: 0.5s ease-in;
} */
</style>
