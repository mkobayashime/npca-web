<template lang="pug">
  .buttonContainer.fi.fi-up(data-emergence="hidden")
    .buttonInner
      p {{label}}
      img(src="/icons/arrow-right.svg" height="55%")
</template>

<script>
export default {
  name: 'NpButton',
  props: {
    label: {
      type: String,
      default: 'Button'
    }
  }
}
</script>

<style lang="stylus" scoped>
.buttonContainer
  display inline-block
  height 50px
  margin-top 50px
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
      background-color #1E4BB2
      transform scale(1.1)
      transition all .3s
    img
      margin 0 15px 0 10px
      transition all .3s
.buttonInner
  margin-top -50px
  display flex
  width 100%
  height 100%
  align-items center
  p
    margin 0 10px 0 25px
    color #fff
    font-size 24px
    font-weight 700
    letter-spacing .1em
    z-index 1
  img
    margin 0 20px 0 0
    transition .2s
    z-index 1
</style>
