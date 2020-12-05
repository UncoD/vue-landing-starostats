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
  min-height: 100vh;

  h1 {
    padding-top: 60px;
  }
}
sup {
  color: red;
}
.order-form {
  margin-top: 60px;

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
      font-size: 20px;
    }
  }

  .order {
    margin-top: 40px;
    height: 60px;
    width: 300px;
    font-size: 25px;
    border-radius: 5px;
    cursor: pointer;
  }
}
</style>
