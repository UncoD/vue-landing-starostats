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
  justify-content: center;
  align-items: center;
  padding: 60px 0;
  min-height: calc(100vh - 120px);
}
.name {
  font-size: 190px;
  text-align: right;
  margin-left: 100px;
  display: block;
  line-height: 1em;
  animation: rightShift ease 2s;
  animation-iteration-count: 1; 
  animation-fill-mode: forwards;
}
.mobile {
  animation: leftShift ease 2s;
  animation-iteration-count: 1; 
  animation-fill-mode: forwards;
  z-index: 1;
} 
@keyframes leftShift { 
  0% { 
    transform: translateX(100%); 
  } 
  100% {
    transform: translateX(0); 
  }
}
@keyframes rightShift { 
  0% { 
    transform: translateX(-100%);
    opacity: 0;
  }
  30% {
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
</style>
