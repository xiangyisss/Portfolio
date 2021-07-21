<template>
  <div class="logo">
    <div class="square square_1"></div>
    <div class="square square_2"></div>
    <div class="square square_3"></div>
    <div class="square square_4"></div>
  </div>
</template>

<script>
export default {
  name: "Logo",
  mounted() {
    this.square1 = document.querySelector(".square_1");
    this.square2 = document.querySelector(".square_2");
    this.square3 = document.querySelector(".square_3");
    this.square4 = document.querySelector(".square_4");
  },
  methods: {
    moveBox(vertical, horizontal) {
      this.square1.style.transform =
        "translateY(-" + vertical + "px)  rotate(45deg)";
      this.square2.style.transform =
        "translateY(" + vertical + "px)  rotate(45deg)";
      this.square3.style.transform =
        "translateX(" + horizontal + "px)  rotate(45deg)";
      this.square4.style.transform =
        "translateX(-" + horizontal + "px)  rotate(45deg)";
      setTimeout(() => {
        this.square1.style.transform = "translateY(0px)  rotate(45deg)";
        this.square2.style.transform = "translateY(0px) rotate(45deg)";
        this.square3.style.transform = "translateX(0px)  rotate(45deg)";
        this.square4.style.transform = "translateX(0px)  rotate(45deg)";
      }, 300);
    },
  },
};
</script>

<style scoped>
* {
  transition: all cubic-bezier(0.68, -0.55, 0.265, 1.55) 0.3s;
}
.logo {
  width: 3rem;
  height: 3rem;
  border-radius: 100%;
  background: linear-gradient(193.13deg, #44a7c3 7.05%, #015871 87.55%);
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: relative;
}

.square_1 {
  top: 18%;
  left: 40%;
  /* transform: translateY(-10px) rotate(45deg); */
}

.square_2 {
  bottom: 19%;
  left: 40%;
  /* transform: translateY(10px) rotate(45deg); */
}

.square_3 {
  top: 40%;
  left: 20%;
}
.square_4 {
  top: 40%;
  right: 19%;
  /* transform: translateX(-10px) rotate(45deg); */
}

.square {
  width: 0.6rem;
  height: 0.6rem;
  background-color: rgb(246, 246, 248);
  transform: rotate(45deg);
  /* box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25); */
  position: absolute;
}
</style>
