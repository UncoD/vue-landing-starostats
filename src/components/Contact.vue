<template>
  <div class="contact">
    <h1>Свяжитесь с нами</h1>
    <form action="" class="order-form">
      <div class="block-1">
        <label class="field">
          <div>Имя<sup>*</sup></div>
          <input type="text">
        </label>
        <label class="field">
          <div>Фамилия<sup>*</sup></div>
          <input type="text">
        </label>
      </div>
      <div class="block-2">
        <label class="field">
          <div>Email<sup>*</sup></div>
          <input type="text">
        </label>
        <label class="field">
          <div>Номер телефона</div>
          <input type="text">
        </label>
      </div>
      <button type="button" class="order">
        Заказать прямо сейчас!
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style lang="scss" scoped>
.contact {
  background: #2a244739;
  color: #111f3b;
  padding: 60px 0;
  min-height: calc(100vh - 120px);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
sup {
  color: red;
}
.order-form {
  margin-top: 20px;

  .block-2 {
    margin-top: 20px;
  }

  .field {
    div {
      margin-top: 10px;
    }
    
    input {
      width: 280px;
      height: 40px;
      margin-top: 10px;
      border-radius: 5px;
      padding: 0 10px;
      font-size: 30px;
      font-family: 'Amatic SC';
      font-weight: bold;
    }
  }

  .order {
    margin-top: 40px;
    height: 60px;
    width: 300px;
    font-size: 30px;
    border-radius: 5px;
    cursor: pointer;
    background: #DB4437;
    outline: none;
    border: 1ps solid #BFBFBF;
    font-family: 'Amatic SC', cursive;
  }
}
</style>
