<template>
  <div class="info">
    <Mobile />
    <p class="name">Старо<br><span class="red-text">Stats</span></p>
  </div>
</template>

<script>
import Mobile from './Mobile.vue'
export default {
  name: 'Info',
  components: {
    Mobile
  }
}
</script>

<style lang="scss" scoped>
.info {
  color: #bac2e7;
  background: #2a2447;
  display: flex;
  min-height: 100vh;
}
.mobile {
  margin: 80px 0 0 350px;
}
.name {
  font-size: 190px;
  text-align: right;
  margin: 0 50px;
  display: block;
  flex: 1;
}
</style>
