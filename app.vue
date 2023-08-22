<template>
  <!-- <div class="hover-ctn">
    <p>Test hover</p>
  </div> -->
  <div class="img-ctn">
    <div class="wrapper">
      <div class="back">
        <h3>Back</h3>
        <p>This is Back</p>
      </div>
      <div class="front">
        <h3>Front</h3>
        <p>This is front</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.img-ctn {
  width: 400px;
  height: 300px;
}
.wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: all 1s cubic-bezier(0.7, -0.5, 0.3, 1.8);
  transform-style: preserve-3d;
}
.img-ctn:hover .wrapper  {
  transform: rotateX(180deg);
}
.front, .back {
  color: #fff;
  position: absolute;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  width: 100%;
  height: 100%;
}
.front {
  background: rgb(2, 32, 32);
}
.back {
  background-color: blueviolet;
  transform: rotateX(180deg);
}

  .hover-ctn {
    width: 10vw;
    height: 5vh;
    border: 1px solid #000;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }
  p {
    height: 20px;
  }
  p:before {
    content: '';
    height: 20px;
    width: inherit;
    min-width: 10vw;
    position: absolute;
    left: 0;
    z-index: -1;
    transform-origin: left;
  }
  p:hover::before {
    animation: swiperight 0.2s forwards ease-in;
    background: rgb(7, 2, 2, 0.5);
  }
  p:after {
    content: '';
    height: 30px;
    width: inherit;
    min-width: 10vw;
    position: absolute;
    left: 0;
    z-index: -2;
    transform-origin: right;
  }
  p:hover::after {
    animation: swipeleft 0.1s forwards ease-in;
    background: rgb(147, 73, 73, 0.4);
  }


  @keyframes swiperight {
    0% {
      transform: scaleX(0%);
    }
    100% {
      transform: scaleX(100%);
    }
  }
  @keyframes swipeleft {
    0% {
      transform: scaleX(-0%);
    }
    100% {
      transform: scaleX(100%);
    }
  }
</style>