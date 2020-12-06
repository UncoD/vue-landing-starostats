<template>
  <div class="main">
    <Info/>
    <Problem class="fade-in full-width" />
    <Adventages class="fade-in full-width" />
    <Contact class="fade-in full-width" />
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
  },
  data() {
    return {
      fadeInElements: []
    }
  },
  mounted() {
    this.fadeInElements = Array.from(document.getElementsByClassName('fade-in'))
    document.addEventListener('scroll', this.handleScroll)
    this.handleScroll()
  },
  unmounted() {
    document.removeEventListener('scroll', this.handleScroll)
  },
  methods:{
    handleScroll() {
      for (var i = 0; i < this.fadeInElements.length; i++) {
        const elem = this.fadeInElements[i]
        if (this.isElemVisible(elem)) {
          elem.style.opacity = '1'
          elem.style.transform = 'translateY(0)'
          this.fadeInElements.splice(i, 1)
        }
      }
    },
    isElemVisible(el) {
      var rect = el.getBoundingClientRect()
      var elemTop = rect.top - window.innerHeight
      var elemBottom = rect.bottom
      return elemTop < window.innerHeight && elemBottom >= 0
    }
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

.fade-in {
  transform: translateY(100%);
  opacity: 0;
  transition: transform 0.3s ease-out, opacity 0.8s ease-out;
}
</style>
