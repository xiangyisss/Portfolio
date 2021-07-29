<template>
  <div class="button">
    <button><slot>Submit</slot></button>
  </div>
</template>

<style scoped>
button {
  width: 6.875rem;
  height: 2.75rem;
  /* text-align: center; */
  font-size: 1rem;
  font-weight: 600;
  border: 2px solid #4560be;
  color: #4560be;
  border-radius: 4px;
  position: relative;
  overflow: hidden;
  z-index: 1;
  cursor: pointer;
  background: transparent;
}

button::before {
  content: " ";
  width: 6.875rem;
  height: 2.75rem;
  background-color: #44a8c344;
  border: none;
  position: absolute;
  z-index: -1;
  left: 0;
  top: -0.125rem;
  border-radius: 4px;
  transform: translateX(-6.875rem);
}

button:hover::before {
  transform: translateX(0%);
  transition: all 0.2s ease;
}
</style>
