<template>
  <div class="logo">
    <div ref="square1" class="square square_1"></div>
    <div ref="square2" class="square square_2"></div>
    <div ref="square3" class="square square_3"></div>
    <div ref="square4" class="square square_4"></div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "Logo",
  setup() {
    let square1 = ref(null);
    let square2 = ref(null);
    let square3 = ref(null);
    let square4 = ref(null);

    // onMounted(() => {
    //   square1.value = document.querySelector(".square_1");
    //   square2.value = document.querySelector(".square_2");
    //   square3.value = document.querySelector(".square_3");
    //   square4.value = document.querySelector(".square_4");
    // });

    function moveBox(vertical, horizontal) {
      square1.value.style.transform =
        "translateY(-" + vertical + "px)  rotate(45deg)";
      square2.value.style.transform =
        "translateY(" + vertical + "px)  rotate(45deg)";
      square3.value.style.transform =
        "translateX(" + horizontal + "px)  rotate(45deg)";
      square4.value.style.transform =
        "translateX(-" + horizontal + "px)  rotate(45deg)";
      setTimeout(() => {
        square1.value.style.transform = "translateY(0px)  rotate(45deg)";
        square2.value.style.transform = "translateY(0px) rotate(45deg)";
        square3.value.style.transform = "translateX(0px)  rotate(45deg)";
        square4.value.style.transform = "translateX(0px)  rotate(45deg)";
      }, 300);
    }

    return {
      moveBox,
      square1,
      square2,
      square3,
      square4,
    };
  },
  // mounted() {
  //   this.square1 = document.querySelector(".square_1");
  //   this.square2 = document.querySelector(".square_2");
  //   this.square3 = document.querySelector(".square_3");
  //   this.square4 = document.querySelector(".square_4");
  // },
  // methods: {
  //   moveBox(vertical, horizontal) {
  //     this.square1.style.transform =
  //       "translateY(-" + vertical + "px)  rotate(45deg)";
  //     this.square2.style.transform =
  //       "translateY(" + vertical + "px)  rotate(45deg)";
  //     this.square3.style.transform =
  //       "translateX(" + horizontal + "px)  rotate(45deg)";
  //     this.square4.style.transform =
  //       "translateX(-" + horizontal + "px)  rotate(45deg)";
  //     setTimeout(() => {
  //       this.square1.style.transform = "translateY(0px)  rotate(45deg)";
  //       this.square2.style.transform = "translateY(0px) rotate(45deg)";
  //       this.square3.style.transform = "translateX(0px)  rotate(45deg)";
  //       this.square4.style.transform = "translateX(0px)  rotate(45deg)";
  //     }, 300);
  //   },
  // },
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
  background: linear-gradient(193.13deg, #88a0f4 7.05%, #4560be 87.55%);
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
