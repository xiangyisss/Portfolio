<template>
  <div class="logo">
    <div class="big-square">
      <div class="square square-1"></div>
      <div class="square square-2"></div>
    </div>
    <div class="square square-3"></div>
  </div>
</template>

<script>
export default {
  name: "Logo",
  mounted() {
    this.square1 = document.querySelector(".square-1");
    this.square2 = document.querySelector(".square-2");
    this.square3 = document.querySelector(".square-3");
  },
  methods: {
    moveBox(vertical, horizontal) {
      this.square1.style.transform =
        "translateY(-" + vertical + "px)  rotate(45deg)";
      this.square2.style.transform =
        "translateY(" + vertical + "px)  rotate(45deg)";
      this.square3.style.transform =
        "translateX(" + horizontal + "px)  rotate(45deg)";
      setTimeout(() => {
        this.square1.style.transform = "translateY(-10px)  rotate(45deg)";
        this.square2.style.transform = "translateY(10px) rotate(45deg)";
        this.square3.style.transform = "translateX(0px)  rotate(45deg)";
      }, 300);
    },
  },
};
</script>

<style scoped>
.logo {
  width: 18.75rem;
  height: 18.75rem;
  border-radius: 100%;
  margin-left: -140px;
  margin-right: 100px;
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
  display: flex;
  justify-content: center;
  align-items: center;
  padding-left: 40px;
}

.big-square {
  position: relative;
}

.square-1,
.square-2 {
  width: 7.5rem;
  height: 7.5rem;
  background-color: rgb(246, 246, 248);
  transform: rotate(45deg);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
}

.square-1 {
  transform: translateY(-10px) rotate(45deg);
}

.square-2 {
  transform: translateY(10px) rotate(45deg);
}

.square-3 {
  width: 5rem;
  height: 5rem;
  background-color: rgb(246, 246, 248);
  transform: rotate(45deg);
  box-shadow: 0px 12px 14px rgba(0, 0, 0, 0.25);
}
</style>
