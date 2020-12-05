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
      <div class="gray-rect" />
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
      <img class="logo" src="../assets/examples/AttendanceList.png">
      <div class="att-students">
        <button
          v-for="(at, student) in students"
          :key="student"
          :class="'att-student ' + (at ? 'active' : '')"
          @click="students[student] = !students[student]"
        >
          {{ student }}
        </button>
      </div>
    </div>
    <div
      v-show="isRep"
      class="inner-mobile report"
    >
      <!--<p class="name">Отчет</p>-->
      <img class="logo" src="../assets/examples/Report.png">
      <div class="rep-students">
        <div
          v-for="(at, student) in students"
          :key="student"
          class="rep-student"
        >
          <div class="rep-name">{{ student }}</div>
          <div class="rep-number">{{ 5 + Math.floor(Math.random() * Math.floor(15)) }}</div>
        </div>
      </div>
    </div>
    <div
      v-show="isSch"
      class="inner-mobile schedule"
    >
      <!--<p class="name">Расписание</p>-->
      <img class="logo" src="../assets/examples/Schedule.png">
      <div class="week-btns">
        <button
          :class="'week-btn ' + (isUpLine ? 'active' : '')"
          @click="isUpLine = true"
        >
          Над чертой
        </button>
        <button
          :class="'week-btn ' + (isUpLine ? '' : 'active')"
          @click="isUpLine = false"
        >
          Под чертой
        </button>
      </div>
      <div class="lesson">
        {{ isUpLine ? 'УПП' : 'РАТППС'}}
      </div>
    </div>
    <div
      v-show="isStu"
      class="inner-mobile students"
    >
      <!--<p class="name">Список студентов</p>-->
      <img class="logo" alt="UncoD" src="../assets/examples/StudentsList.png">
      <div class="stu-students">
        <div
          v-for="(at, student) in students"
          :key="student"
          class="stu-student"
        >
          {{ student }}
        </div>
      </div>
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
      isStu: false,
      students: {
        "Иванов И.В.": false,
        "Васильева Л.Ю.": false,
        "Грибоедов К.Ф.": false,
        "Касаткина В.П.": false,
        "Авдеева О.Л.": false
      },
      isUpLine: true
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
  left: -85%;
  top: 110px;
  transform: rotate(-50deg);
  font-size: 45px;
}
.test-text-br {
  position: absolute;
  right: -60%;
  top: 450px;
  transform: rotate(50deg);
  font-size: 35px;
}
.btn-back {
  position: absolute;
  right: 36px;
  top: 103px;
  width: 56px;
  height: 56px;
  border-radius: 50%;
  cursor: pointer;
  background: transparent;
  border: 3px dashed #17AB13;
  z-index: 500;
  outline: none;
  animation: spin 5s linear infinite;
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
  width: 268px;
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

  .gray-rect {
    background: #C4C4C4;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 17px;
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

  &.attendance {
    .att-students {
      position: absolute;
      width: 198px;
      height: 300px;
      background: #FFFBF4;
      top: 161px;
      left: 25px;
      border: 1px solid #BFBFBF;
      border-radius: 5px;
      display: flex;
      flex-direction: column;
      padding: 10px;

      .att-student {
        font-family: 'Amatic SC';
        font-weight: bold;
        background: #FFAEAE;
        height: 45px;
        font-size: 28px;
        text-align: left;
        outline: none;
        border: 1px solid #BFBFBF;
        border-radius: 5px;
        margin: 2px 0;
        padding: 0 0 0 15px;
        cursor: pointer;
        &.active{
          background: #AAFF82;
        }
      }
    }
  }
  &.students {
    .stu-students {
      position: absolute;
      width: 198px;
      height: 400px;
      background: #FFFBF4;
      top: 110px;
      left: 25px;
      border: 1px solid #BFBFBF;
      border-radius: 5px;
      display: flex;
      flex-direction: column;
      padding: 10px;

      .stu-student {
        font-family: 'Amatic SC';
        font-weight: bold;
        background: white;
        height: 45px;
        font-size: 28px;
        text-align: left;
        outline: none;
        border: 1px solid #BFBFBF;
        border-radius: 5px;
        margin: 2px 0;
        padding: 0 0 0 15px;
        line-height: 45px;
      }
    }
  }
  &.report {
    .rep-students {
      position: absolute;
      width: 198px;
      height: 400px;
      background: #FFFBF4;
      top: 110px;
      left: 25px;
      border: 1px solid #BFBFBF;
      border-radius: 5px;
      display: flex;
      flex-direction: column;
      padding: 10px;

      .rep-student {
        font-family: 'Amatic SC';
        font-weight: bold;
        background: white;
        height: 45px;
        font-size: 28px;
        text-align: left;
        outline: none;
        border: 1px solid #BFBFBF;
        border-radius: 5px;
        margin: 2px 0;
        padding: 0 0 0 15px;
        line-height: 45px;
        display: flex;

        .rep-name {
          flex: 1;
        }
        .rep-number {
          border-left: 1px solid black;
          padding: 0 10px;
          width: 15px;
          text-align: center;
        }
      }
    }
  }
  &.schedule {
    .lesson {
      position: absolute;
      top: 173px;
      left: 70px;
      background: #F8F8F8;
      font-size: 32px;
    }
    .week-btns {
      position: absolute;
      top: 110px;
      left: 25px;

      .week-btn {
        font-family: 'Amatic SC';
        font-weight: bold;
        font-size: 28px;
        width: 110px;
        height: 48px;
        background: white;
        border: 2px solid black;
        outline: none;
        cursor: pointer;

        &.active {
          border: 2px solid #ED0C0C;
        }
      }
    }
  }
}
</style>
