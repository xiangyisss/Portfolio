<template>
  <div class="projects_page">
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
import { onMounted } from "vue";
export default {
  name: "Projects",
  setup() {
    onMounted(() => {
      let items = document.querySelectorAll(".items");
      setTimeout(() => {
        items.forEach((item) => {
          item.style.opacity = "1";
          item.style.transform = "translate(0)";
        });
      }, 0);
    });
  },
  // mounted() {
  // },
};
</script>

<style scoped>
* {
  transition: all 0.4s ease-in;
}

.projects_page {
  width: 60%;
  margin-top: 10vh;
  padding: 1rem;
}

.header {
  margin-bottom: 1rem;
  padding: 1rem;
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
  width: 9rem;
  height: 9rem;
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
  width: 9rem;
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
  /* transform: scale(0.8); */
  transform: translateY(50px);
}

@media (max-width: 600px) {
  .projects_page {
    width: 90%;
    margin-top: 10vh;
  }
  .projects {
    flex-direction: column;
  }
  .project {
    margin-bottom: 1rem;
  }
}
</style>
