<template>
  <div class="mobile">
    <p class="test-text">Попробуй уже сейчас!</p>
    <p class="test-text-br">(можно потыкать,<br>но чуть-чуть)</p>
    <img src="../assets/smartphone.png">
    <button
      v-show="isAtt || isRep || isSch || isStu"
      class="btn-back"
      @click="returnMenu"
    ><!--&#9668;--></button>
    <div
      v-show="!(isAtt || isRep || isSch || isStu)"
      class="inner-mobile menu"
    >
      <p class="name">Старо<span class="red-text">Stats</span></p>
      <div class="buttons">
        <button class="btn attendance" @click="setPage(0)">Посещаемость</button>
        <button class="btn report" @click="setPage(1)">Отчет</button>
        <button class="btn schedule" @click="setPage(2)">Расписание</button>
        <button class="btn students" @click="setPage(3)">Список студентов</button>
      </div>
    </div>
    <div
      v-show="isAtt"
      class="inner-mobile attendance"
    >
      <!--<p class="name">Посещаемость</p>-->
      <img class="logo" alt="UncoD" src="../assets/examples/AttendanceList.png">
    </div>
    <div
      v-show="isRep"
      class="inner-mobile report"
    >
      <!--<p class="name">Отчет</p>-->
      <img class="logo" alt="UncoD" src="../assets/examples/Report.png">
    </div>
    <div
      v-show="isSch"
      class="inner-mobile schedule"
    >
      <!--<p class="name">Расписание</p>-->
      <img class="logo" alt="UncoD" src="../assets/examples/Schedule.png">
    </div>
    <div
      v-show="isStu"
      class="inner-mobile students"
    >
      <!--<p class="name">Список студентов</p>-->
      <img class="logo" alt="UncoD" src="../assets/examples/StudentsList.png">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Mobile',
  data() {
    return {
      isAtt: false,
      isRep: false,
      isSch: false,
      isStu: false
    }
  },
  methods: {
    setPage(num) {
      switch(num) {
        case 0:
          this.isAtt = true
          break
        case 1:
          this.isRep = true
          break
        case 2:
          this.isSch = true
          break
        case 3:
          this.isStu = true
          break
      }
    },
    returnMenu() {
      this.isAtt = false
      this.isRep = false
      this.isSch = false
      this.isStu = false
    }
  }
}
</script>

<style lang="scss" scoped>
.mobile {
  position: relative;
  padding-bottom: 60px;
  img {
    max-width: 100%;
  }
}
.test-text {
  position: absolute;
  left: -100%;
  top: 110px;
  transform: rotate(-50deg);
  font-size: 35px;
}
.test-text-br {
  position: absolute;
  right: -60%;
  top: 450px;
  transform: rotate(50deg);
  font-size: 25px;
}
.btn-back {
  position: absolute;
  right: 34px;
  top: 104px;
  width: 56px;
  height: 56px;
  border-radius: 50%;
  cursor: pointer;
  /*background: #003580;
  color: #d0ff00;*/
  background: transparent;
  border: 3px dashed #17AB13;
  z-index: 1;
  outline: none;
  animation: spin 5s linear infinite;;
}
@keyframes spin {
  from {
    transform: rotate(0);
  }

  to {
    transform: rotate(360deg);
  }
}
.inner-mobile {
  width: 270px;
  height: 450px;
  position: absolute;
  top: 65px;
  left: 18px;
  color: black;
  overflow: hidden;

  .name {
    margin-top: 60px;
    font-size: 40px;
  }

  .buttons {
    margin-top: 30px;
    padding: 0 30px;
    display: flex;
    flex-direction: column;

    .btn {
      margin: 10px 0;
      height: 45px;
      text-transform: uppercase;
      outline: none;
      border-radius: 5px;
      border: 1px solid #BFBFBF;
      font-size: 24px;
      font-family: 'Amatic SC', cursive;
      cursor: pointer;

      &.attendance {
        background: #FFC95F;
      }
      &.report {
        background: #E8EC3D;
      }
      &.schedule {
        background: #73D9D9;
      }
      &.students {
        background: #FD89FF;
      }
    }
  }
}
</style>
