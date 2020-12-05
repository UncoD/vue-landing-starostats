<template>
  <div class="info">
    <div class="container">
      <div>
        <Mobile />
        <p class="name">Старо<br><span class="red-text">Stats</span></p>
      </div>
    </div>
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
.name {
  font-size: 190px;
  text-align: right;
  margin-left: 100px;
  display: block;
  flex: 1;
  align-self: flex-start;
  margin-right: -200px;
  line-height: 1em;
}
.container {
  flex-direction: row;
  >div {
    display: flex;
  }
}
</style>
