<template>
  <div class="advantages">
    <h1>Как всё работает?</h1>
    <div class="advantages-container">
      <div class="left-block">
        <p>Управление списком студентов</p>
        <p>Передача данных в деканат</p>
        <p>Дружественный интерфейс</p>
      </div>
      <div class="mobile">
        <img class="smart-img" src="../assets/smartphone.png">
        <iframe class="app-video"
          src="https://www.youtube.com/embed/QEN3l1EPrTE?controls=0&autoplay=1&loop=1">
        </iframe>
      </div>
      <div class="right-block">
        <p>Управление расписанием</p>
        <p>Автоматический подсчет пропусков</p>
        <p>Мобильная платформа</p>
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
.advantages {
  background: #2a24475e;
  color: #1c2f54;
  padding: 60px 0;
  min-height: calc(100vh - 120px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.advantages-container {
  margin-top: 20px;
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
    p {
      width: 195px;
      font-size: 40px;
      margin: 30px 0;
      padding: 15px;
      cursor: default;

      &:hover {
        transform: scale(1.2);
        background: #FEFEFE;
        border-radius: 20px;
        color: #2d3051;
      }
    }
  }
}

@media screen and (max-width: 1140px) {
  .advantages-container {
    .left-block, .right-block {
      p {
        &:hover {
          transform: scale(1.04);
        }
      }
    }
  }
}
</style>
