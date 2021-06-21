<template>
  <div class="notfound">
    <h1 class="title">404 - Page Not Found</h1>
    <p>The page you are looking for doesn't exist.</p>
    <router-link :to="{ name: 'Home' }">
      <p class="text">
        Go back to the <span class="highlight">Home</span> page
      </p>
    </router-link>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.notfound {
  background-image: url(../assets/NotFoundImage.jpg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  color: whitesmoke;
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
}
.highlight {
  color: rgb(255, 131, 43);
}
</style>
