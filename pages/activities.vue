<template lang="pug">
  .nuxtContainer
    .title
      h1
        .line.line1
          span A
          span c
          span t
          span i
          span v
          span i
          span t
          span i
          span e
          span s
      h2.fi.fi-up(data-emergence="hidden") 活動・実績
    section(v-for="section in sections")
      np-section-activities(:section="section")
    .footerSpacer
</template>

<script>
import anime from 'animejs'
import emergence from 'emergence.js'
import NpSeparator from '~/components/NpSeparator.vue'
import NpSection from '~/components/NpSection.vue'
import NpSectionActivities from '~/components/NpSectionActivities.vue'
import sections from '~/static/activities.json'
export default {
  components: { NpSeparator, NpSection, NpSectionActivities },
  data() {
    return {
      sections: sections
    }
  },
  mounted() {
    const h1 = document.querySelector('.title h1')
    h1.style.opacity = 1
    ;(this.anime = anime.timeline({}).add({
      targets: '.line1 span',
      translateY: ['1.2em', 0],
      duration: 500,
      delay: function(el, i) {
        return 50 * i + 500
      },
      easing: 'easeOutQuart'
    })),
      (this.anime = anime.timeline({}).add({
        targets: '.line2 span',
        translateY: ['1.2em', 0],
        duration: 500,
        delay: function(el, i) {
          return 50 * i + 700
        },
        easing: 'easeOutQuart'
      }))
    emergence.init({
      reset: false,
      offsetBottom: 100
    })
    const removeClass = document.documentElement.classList.remove('emergence')
    document.documentElement.scrollTop = 1
  }
}
</script>

<style lang="stylus">
.title
  width 800px
  margin 80px auto 0
  color #000
  h1
    font-size 100px
    font-weight 700
    opacity 0
    .line
      overflow hidden
      margin 0
      span
        display inline-block
        margin-right 15px
  h2
    margin-top 30px
    font-size 30px
    font-family 'Noto Sans JP'
    font-weight 700

section
  width 800px
  margin 0 auto

.footerSpacer
  height 200px
</style>
