<template lang="pug">
section.app-header
  a.logo
    img(src="~/assets/images/logo1.png")
  .menu 
    .nav 
      NavigationD  
    .buttons
      a(href="#") Sign up
      button.btn Get Started
  .menuM
    .hamburger(@click="toggle()")
      img(src="~/assets/images/menu.png")      
    .nav
      NavigationM(:open="open")
      
</template>
<script>
import NavigationD from '~/components/NavigationD.vue'
import NavigationM from '~/components/NavigationM.vue'
export default {
  data () {
    return {
      open: false
    }
  },
  components: {
    NavigationD,
    NavigationM
  },
  methods: {
    toggle(){
      this.open = !this.open
    },
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.app-header
  display: flex
  .logo
    img
      width: 10rem
  .menu

    @include flex
    .buttons
      margin-left: 15rem
      a
        color: #611f69
        padding: 1.5rem
      button
        background: #611f69 
    @media (max-width: 1200px) 
      display: none     
  .menuM 
    position: relative 
    .hamburger
      width: 1.5rem
      height: 1.5rem
      background: black
      right: 0
      cursor: pointer
      z-index: 20
      // padding: $space*2
      @include absolute-e  
    @media (min-width: 1200px) 
      display: none    
</style>
