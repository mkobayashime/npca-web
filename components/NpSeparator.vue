<template lang="pug">
  .separator(data-emergence="hidden")
</template>

<script>
import emergence from 'emergence.js'
export default {
  name: 'Separator',
  mounted() {
    emergence.init({
      reset: false
    })
  }
}
</script>

<style lang="stylus" scoped>
.separator
  margin-top 100px
  width 50px
  height 3px
  background-color #555555
  &[data-emergence=hidden]
    transform-origin center left
    transform translateX(-30px) scaleX(0)
  &[data-emergence=visible]
    transform-origin center left
    transform translateX(0) scaleX(1)
    transition all .5s cubic-bezier(.4, 1.87, .47, .82)
</style>
