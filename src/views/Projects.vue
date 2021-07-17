<template>
  <div class="projects-page">
    <div class="header items">
      <h1 class="text">What I've built</h1>
    </div>
    <div class="projects items">
      <div class="project"></div>
      <div class="project"></div>
      <div class="project"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Projects",
  mounted() {
    let items = document.querySelectorAll(".items");
    setTimeout(() => {
      items.forEach((item) => {
        item.style.opacity = "1";
        item.style.transform = "scale(1)";
      });
    }, 0);
  },
};
</script>

<style scoped>
* {
  transition: all 0.3s ease-in;
}

.projects-page {
  width: 60%;
  margin-top: 10vh;
}

.header {
  margin-bottom: 2rem;
}

.text {
  text-align: center;
}

.projects {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 1rem;
}
.project {
  width: 12.5rem;
  height: 12.5rem;
  /* border: 2px solid steelblue; */
  border-radius: 4px;
  cursor: pointer;
  background-image: url("../assets/project.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  position: relative;
  overflow: hidden;
}

.project::after {
  content: "Project-Name";
  width: 12.5rem;
  height: 1.875rem;
  background-color: rgba(0, 0, 0, 0.356);
  border-bottom-right-radius: 4px;
  border-bottom-left-radius: 4px;
  position: absolute;
  bottom: 0;
  left: 0;
  text-align: center;
  line-height: 1.875rem;
  color: whitesmoke;
  transform: translateY(1.875rem);
}

.project:hover::after {
  transform: translateY(0);
  transition: all 0.2s ease-in;
}

.items {
  opacity: 0;
  transform: scale(0.8);
}
</style>
