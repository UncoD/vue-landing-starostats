<template>
  <div class="adventages">
    <h1>Как всё работает?</h1>
    <div class="container">
      <div class="left-block">
        <p>Преимущество</p>
        <p>Преимущество</p>
        <p>Преимущество</p>
      </div>
      <div class="mobile">
        <img class="smart-img" src="../assets/smartphone.png">
        <iframe class="app-video"
          src="https://www.youtube.com/embed/QEN3l1EPrTE?controls=0&autoplay=1&loop=1">
        </iframe>
      </div>
      <div class="right-block">
        <p>Преимущество</p>
        <p>Преимущество</p>
        <p>Преимущество</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Adventages'
}
</script>

<style lang="scss" scoped>
.adventages {
  background: #2a24475e;
  color: #1c2f54;
  min-height: 100vh;

  h1 {
    padding-top: 60px;
  }
}
.container {
  margin-top: 50px;
  display: flex;
  justify-content: center;

  .mobile {
    margin: 0 50px;
    position: relative;

    .smart-img {
      width: 300px;
      height: 600px;
      object-fit: cover;
    }

    .app-video {
      position: absolute;
      left: 0;
      top: 0;
      width: 278px;
      height: 462px;
      top: 68px;
      left: 12px;
      border: none;
    }
  }

  .left-block, .right-block {
    margin-top: 30px;

    p {
      height: 200px;
    }
  }
}
</style>
