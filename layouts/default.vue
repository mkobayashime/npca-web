<template lang="pug">
  #root
    the-sidebar#theSidebar
    #scrollArea
      nuxt
</template>

<script>
import TheSidebar from '~/components/TheSidebar.vue'
export default {
  components: { TheSidebar }
}
</script>

<style lang="stylus">
html
  font-size 16px
  font-family 'Roboto', 'Noto Sans JP', sans-serif
  -ms-text-size-adjust 100%
  -webkit-text-size-adjust 100%
  -moz-osx-font-smoothing grayscale
  -webkit-font-smoothing antialiased
  box-sizing border-box

*,
*:before,
*:after
  box-sizing border-box
  margin 0

#theSidebar
  width 340px
  height 100%
  display fixed
  overflow hidden

#scrollArea
  margin-left 340px
  width calc(100% - 340px)
  overflow-x hidden
</style>
