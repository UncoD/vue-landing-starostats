<template>
  <div class="problem">
    <div class="container">
      <h1>Зачем и почему?</h1>
      <div class="problems-container">
        <div class="problem-block right">
          <p class="problem-text">Постоянно переписываете список студентов группы?</p>
          <img class="problem-image" src="../assets/problem.png">
        </div>
        <div class="problem-block left">
          <img class="problem-image " src="../assets/problem.png">
          <p class="problem-text">Каждый день заполняете список прошедших пар?</p>
        </div>
        <div class="problem-block right">
          <p class="problem-text">Вручную подсчитываете количество пропусков за несколько недель учебы?</p>
          <img class="problem-image" src="../assets/problem.png">
        </div>
        <div class="problem-block left">
          <img class="problem-image" src="../assets/problem.png">
          <p class="problem-text">Ходите в деканат, чтобы передать данные о пропусках?</p>
        </div>
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
  min-height: 100vh;
  padding-bottom: 60px;

  h1 {
    padding-top: 60px;
  }
}
.problems-container {
  margin-top: 80px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 80px;
  row-gap: 80px;

  .problem-block {
    display: flex;

    .problem-image {
      width: 200px;
      height: 200px;
    }
    .problem-text {
      flex: 1;
      padding: 20px 0;
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
</style>
