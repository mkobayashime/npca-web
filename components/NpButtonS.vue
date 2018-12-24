<template lang="pug">
  .buttonContainerS.fi.fi-up(data-emergence="hidden")
    .buttonInner
      p
        slot
      img(src="/icons/arrow-right.svg" height="55%")
</template>

<script>
export default {
  name: 'NpButtonS',
  props: {
    label: {
      type: String,
      default: 'Button'
    }
  }
}
</script>

<style lang="stylus" scoped>
.buttonContainerS
  display inline-block
  height 25px
  margin 0 15px 10px 0
  &:before
    content ''
    display block
    width 100%
    height 100%
    border-radius 25px
    background-color #8b8b8b
    z-index 0
    transform scale(1)
    transition all .3s
  &:hover
    &:before
      transform scale(1.1)
      transition all .3s
    img
      margin 0 15px 0 10px
      transition all .3s
  .buttonInner
    margin-top -25px
    display flex
    width 100%
    height 100%
    align-items center
    p
      margin 0 10px 0 25px
      color #fff
      font-size 12px
      letter-spacing .1em
      z-index 1
    img
      margin 0 20px 0 0
      transition .2s
      z-index 1
</style>
