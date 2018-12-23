<template lang="pug">
  .theSidebar
    .theSidebarTop
      nuxt-link(to="/")
        img.logotype-jp.sidebarAnim(src="/logotype-jp.svg" width="250px")
      nuxt-link(to="/activities" tag="div")
        np-sidebar-indicator
          p.sidebarAnim(slot="label") Activities
          p.sidebarAnim(slot="labelJp") 活動・実績
      nuxt-link(to="/works" tag="div")
        np-sidebar-indicator
          p.sidebarAnim(slot="label") Works
          p.sidebarAnim(slot="labelJp") 作品
      nuxt-link(to="/contact" tag="div")
        np-sidebar-indicator
          p.sidebarAnim(slot="label") Contact
          p.sidebarAnim(slot="labelJp") 連絡先
    .theSidebarBottom
      img.logotype-full(src="/logotype-full.svg" width="120px")
</template>

<script>
import anime from 'animejs'
import NpSidebarIndicator from '~/components/NpSidebarIndicator'
export default {
  name: 'TheSidebar',
  components: { NpSidebarIndicator },
  mounted() {
    this.anime = anime.timeline({}).add({
      targets: '.sidebarAnim',
      translateY: ['30px', 0],
      opacity: [0, 1],
      duration: 500,
      delay: function(el, i) {
        return 50 * i + 1000
      },
      easing: 'easeOutQuart'
    })
  }
}
</script>

<style lang="stylus" scoped>
.theSidebar
  width 100%
  height 100%
  display flex
  align-items center
  justify-content space-between
  flex-direction column
  position fixed
  background-color #000
  .logotype-jp
    margin 50px 0 40px
  .theSidebarBottom
    width 100%
    height 40%
    display flex
    flex-direction column
    align-items center
    justify-content flex-end
    background-size cover
    background-blend-mode normal, color
    background-image linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(0, 0, 0, 0.2) 50%), linear-gradient(to right top, #0f42c2, #0077e9, #009edf, #00beb3, #1ed87f), url(/img/bg-2.jpg)
    .logotype-full
      margin 20px 0
</style>
