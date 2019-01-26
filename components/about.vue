<template lang="pug">
section.about
  .container
    .heading
      h1 Imagine what you’ll accomplish together
    .content
      .img-big
        img(src="~/assets/images/img1.jpg")
      .details
        p Slack is a collaboration hub for work, no matter what work you do. It’s a place where conversations happen, decisions are made, and information is always at your fingertips. With Slack, your team is better connected.
        .input
          input(type="e-mail" placeholder="Email Address")
          button.btn Get Started
        .sign  
          p Already using Slack? 
          a(href="#") Sign In
        .img
          img(src="~/assets/images/img2.jpg")
</template>
<script>
export default {
  
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.about
  .container
    .heading
      h1
        text-align: center
        color: black
        font-size: 4rem
        font-weight: 800
    .content
      display: flex
      margin: 2rem 0 0 4rem
      .details
        padding: 1rem
        p
          color: black   
        input
          padding: 1rem
          margin: 1rem
        button
          background: #611f69   
        a 
          color: #611f69
        .sign
          display: flex 
        .img
          img
            width: 20rem  
            height: 20em 
            filter: grayscale(100%)
            &:hover
              border-radius: 5%
</style>
