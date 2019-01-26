<template lang="pug">
  nav.navigator(:class="{open: open}")
    .menu(:class="{open: open}")
      a(href="#")  Why Slack ?
      a(href="#")  Pricing
      a(href="#")  About Us

</template>
<script>
export default {
  
}
</script>
<style lang="sass">
nav.navigator
  .menu
    //  display: block

</style>
