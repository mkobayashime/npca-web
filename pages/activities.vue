<template lang="pug">
  .nuxtContainer
    .title
      h1
        np-page-title(:text="title" :key="index" v-for="title in title")
      h2.fi.fi-up(data-emergence="hidden") 活動・実績
    section(v-for="section in sections")
      np-separator
      np-section-activities(:section="section")
    .footerSpacer
</template>

<script>
import emergence from 'emergence.js'
import NpPageTitle from '~/components/NpPageTitle.vue'
import NpSectionActivities from '~/components/NpSectionActivities.vue'
import NpSeparator from '~/components/NpSeparator.vue'
import sections from '~/static/activities.json'
export default {
  components: { NpPageTitle, NpSectionActivities, NpSeparator },
  data() {
    return {
      title: ['Activities'],
      sections: sections
    }
  },
  mounted() {
    emergence.init({
      reset: false,
      offsetBottom: 100
    })
    const removeClass = document.documentElement.classList.remove('emergence')
    document.documentElement.scrollTop = 1
  }
}
</script>

<style lang="stylus" scoped>
.title
  width 800px
  margin 80px auto 0
  color #000
  h1
    font-size 100px
    font-weight 700
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
