<template>
  <div class="wave">
    <div class="line"></div>
    <div class="line"></div>
  </div>
</template>

<style scoped>
.wave {
  height: 10%;
  width: 100vw;
  position: absolute;
  top: 100vh;
  left: 50vw;
  /* left: 130%; */
  transform: rotate(-90deg);
  /* background: #015871; */
}

.line {
  background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/85486/wave.svg)
    repeat-x;
  position: absolute;
  top: -118px;
  width: 3000vw;
  height: 25vh;
  /* height: 40vh; */
  animation: wave 15s ease-in-out infinite;
  transform: rotate3d(0, 0, 0);
}

.line:nth-of-type(2) {
  top: -113px;
  animation: wave 16s ease-in-out infinite, swell 7s ease -1.25s infinite;
}

@keyframes wave {
  0% {
    margin-left: 0;
  }
  50% {
    margin-left: -2000px;
  }
  100% {
    margin-left: 0;
  }
}

@keyframes swell {
  0% {
    transform: translate3d(0, -25px, 0);
  }
  50% {
    transform: translate3d(0, 5px, 0);
  }
  100% {
    transform: translate3d(0, -25px, 0);
  }
}
</style>
