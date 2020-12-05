<template>
  <div class="main">
    <Info />
    <Problem />
    <Adventages />
    <Contact />
    <img class="logo" alt="UncoD" src="../assets/logo.png">
  </div>
</template>

<script>
import Info from './Info.vue'
import Problem from './Problem.vue'
import Adventages from './Adventages.vue'
import Contact from './Contact.vue'
export default {
  name: 'MainPage',
  components: {
    Info,
    Problem,
    Adventages,
    Contact
  }
}
</script>

<style lang="scss" scoped>
.logo {
  display: none;
  width: 50px;
  height: 50px;
  object-fit: contain;
}
</style>
