<template>
  <div class="problem">
    <h1>Зачем и почему?</h1>
    <div class="problems-container">
      <div class="problem-block right">
        <p class="problem-text">Постоянно переписываете список студентов группы?</p>
        <img class="problem-image" src="../assets/students.jpg">
      </div>
      <div class="problem-block left">
        <img class="problem-image" src="../assets/lessons.jpg">
        <p class="problem-text">Каждый день заполняете список прошедших пар?</p>
      </div>
      <div class="problem-block right">
        <p class="problem-text">Вручную подсчитываете количество пропусков за несколько недель учебы?</p>
        <img class="problem-image" src="../assets/homework.jpg">
      </div>
      <div class="problem-block left">
        <img class="problem-image" src="../assets/paper.png">
        <p class="problem-text">Ходите в деканат, чтобы передать данные о пропусках?</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Problem'
}
</script>

<style lang="scss" scoped>
.problem {
  background: #2a2447af;
  color: #dff9ff;
  padding: 60px 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  min-height: calc(100vh - 120px);
}
.problems-container {
  font-size: 30px;
  margin-top: 80px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 50px;
  row-gap: 50px;
  max-width: 1100px;

  .problem-block {
    display: flex;
    transition: 0.3s;
    padding: 15px;

    &:hover {
      transform: scale(1.2);
      background: #FEFEFE;
      border-radius: 20px;
      color: #2d3051;
    }

    .problem-image {
      width: 200px;
      height: 200px;
      border-radius: 50%;
    }
    .problem-text {
      flex: 1;
      align-self: center;
    }

    &.left {
      .problem-image {
        margin-right: 40px;
      }
      .problem-text {
        text-align: left;
      }
    }

    &.right {
      .problem-image {
        margin-left: 40px;
      }
      .problem-text {
        text-align: right;
      }
    }
  }
}

@media screen and (max-width: 1140px) {
  .problems-container {
    .problem-block {
      &:hover {
        transform: scale(1.1);
      }
    }
  }
}
</style>
