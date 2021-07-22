<template>
  <div class="notfound">
    <h1 class="title">404 - Page Not Found</h1>
    <p>The page you are looking for doesn't exist.</p>
    <router-link :to="{ name: 'Home' }">
      <p class="text">Go back to the Home page</p>
    </router-link>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.notfound {
  width: 100%;
  height: 100vh;
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  color: rgb(236, 231, 225);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.notfound > * {
  margin-bottom: 2rem;
}

a {
  text-decoration: none;
  color: inherit;
}

.text {
  font-size: 1.25rem;
  font-weight: bold;
  color: #2c3e50;
}
</style>
