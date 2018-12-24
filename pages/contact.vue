<template lang="pug">
  .nuxtContainer
    .title
      h1
        np-page-title(:text="title" v-for="title in title")
      h2.fi.fi-up(data-emergence="hidden") 連絡先
    section(v-for="section in sections")
      np-separator
      np-section(:section="section")
    .footerSpacer
</template>

<script>
import emergence from 'emergence.js'
import NpPageTitle from '~/components/NpPageTitle.vue'
import NpSeparator from '~/components/NpSeparator.vue'
import NpSection from '~/components/NpSection.vue'
import sections from '~/static/activities.json'
export default {
  components: { NpPageTitle, NpSeparator, NpSection },
  data() {
    return {
      title: ['Contact'],
      sections: [
        {
          p: [
            'お問い合わせ・取材などのご連絡はこちらのメールアドレスまでお願い致します',
            'webmaster@npca.jp'
          ]
        },
        {
          p: [
            'NPCAは常時入部を受け付けています',
            '東館2階 視聴覚室の向かいの部室まで、気軽にお越しください!',
            '扉に貼られたNの文字のロゴが目印です'
          ]
        }
      ]
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
