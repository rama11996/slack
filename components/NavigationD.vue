<template lang="pug">
nav.navigator(:class="{open: open}")
  ul.primary
    li(v-for="item, i in navigation.primary", :key="i")
      a(href="#", v-scroll-to="item.scroll_to") {{ item.label }}
        img(v-if="item.children", src="~/assets/images/dropdown.png")
      ul.dropdown-content(v-if="item.children")
        li(v-for="child, i in item.children", :key="i")
          nuxt-link(:to="child.url") {{ child.label }}
</template>
<script>
import navigation from 'static/datas/navigation'

export default {
  props: {
    open: {
      type: Boolean,
      required: true
    }
  },
  data(){
    return{
      navigation: navigation
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

.navigator
  overflow: visible
  ul.primary
    @include stack-l
    @include reset-space
    position: relative
    top: $space
    > li
      position: relative
      height: 2rem
      a
        color: black
      .dropdown-content
        display: none
        position: absolute
        top: 100%
        background: #FFF
        z-index: 1000


  ul.primary > li:hover
    > ul.dropdown-content
      display: block
      @include reset-space
      transition: all 0.4s ease
      z-index: 0
      padding: 15px 20px !important
      min-width: 230px
      margin: 0
      border-radius: 0
      -webkit-box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.2)
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.2)
      border: none
      font-size: 1rem
      color: #212529
      text-align: left
      list-style: none
      background-color: #fff
      li
        a
          padding: 12px 10px
          border-bottom: 1px solid rgba(0, 0, 0, 0.07)
          font-size: 14px
          display: block
          color: #222
          text-transform: capitalize !important
          transition: all 0.4s ease
          &:hover
            color: $event-pink
        &:last-child
          a
            border-bottom: none

.navigator
  a
    padding: 0 22px
    text-transform: uppercase
    font-size: 14px
    display: block
    position: relative
    img
      display: inline-block
      @include absolute-se
      top: 0.1rem
      right: -0.3rem
  a.btn.btn-primary
    font-size: 0.9rem
    text-decoration: none
    margin-top: -$space
  @media (max-width: $breakpoint-tab-5)
    display: none

</style>
