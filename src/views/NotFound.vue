<template>
  <div class="notfound">
    <h1>Oops!</h1>
    <router-link :to="{ name: 'Home' }">Go back to the Home page</router-link>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.notfound {
  position: relative;
  z-index: 1;
}
</style>
