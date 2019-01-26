<template lang="pug">
.page
  app-header  
  about
</template>
<script>
import AppHeader from '~/components/app-header.vue'
import About from '~/components/about.vue'
export default {
  components: {
    AppHeader,
    About
  }
}
</script>
<style lang="sass" scoped>

</style>
