<template lang="pug">
  .NpSidebarItem
    .label
      slot(name="label")
    .labelJp
      slot(name="labelJp")
</template>

<script>
export default {
  name: 'NpSidebarItem'
}
</script>

<style lang="stylus" scoped>
.NpSidebarItem
  display flex
  flex-direction column
  align-items center
  justify-content center
  margin 0
  color: hsl(0, 0%, 90%)
  &:before
    content ''
    display block
    width 200px
    height .8em
    transform translateY(30px) scaleX(0)
    transition all .2s
    background-color hsl(0, 0%, 20%)
    z-index -1
  &:hover:before
    transform translateY(30px) scaleX(1)
  .label
    margin-bottom 10px
    p
      color hsl(0, 0%, 90%)
      font-size 24px
      font-weight 700
      letter-spacing .1em
      z-index 1
  .labelJp
    margin-bottom 25px
    p
      font-size 15px
      color hsl(0, 0%, 50%)
      z-index 1
</style>
