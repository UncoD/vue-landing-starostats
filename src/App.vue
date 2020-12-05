<template>
  <div id="app">
    <MainPage />
  </div>
</template>

<script>
import MainPage from './components/MainPage.vue'

export default {
  name: 'App',
  components: {
    MainPage
  }
}
</script>

<style>
@import "./assets/fonts/fonts.css";
body { 
  animation: fadeInAnimation ease 2s;
  animation-iteration-count: 1; 
  animation-fill-mode: forwards; 
  margin: 0;
} 
@keyframes fadeInAnimation { 
  0% { 
    opacity: 0; 
  } 
  100% { 
    opacity: 1; 
  }
}
p, h1 {
  margin: 0;
}
h1 {
  font-size: 60px;
}
#app {
  font-family: 'Amatic SC';
  font-size: 24px;
  font-weight: bold;
  text-align: center;
  color: #2c3e50;
  margin: 0;
}
.red-text {
  color: #DB4437;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  max-width: 1000px;
  min-height: 100vh;
}
</style>
