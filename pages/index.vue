<template lang="pug">
  .nuxtContainer
    .title
      h1
        np-page-title(:text="title" :key="index" v-for="title in title")
      h2.fi.fi-up(data-emergence="hidden") 灘校パソコン研究部へようこそ!
    section(:key="index" v-for="section in sections")
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
      title: ['Hello,', 'World!'],
      sections: [
        {
          title: ['NPCAとは?'],
          p: [
            'NPCA: 灘校パソコン研究部は、灘中学校・高等学校の部活動の1つです',
            '普段から幅広く活動しています',
            '部会以外での招集はなく、自由な雰囲気です'
          ]
        },
        {
          title: ['NPCAの由来'],
          p: [
            "Nada Personal Computer users' Association",
            '直訳すると「灘校パソコン使用者の会」の頭文字を取った愛称です',
            "user'sのuが入らないのは、考案者が語感を重視したためだと言われています",
            '大文字・小文字は特に区別しません'
          ]
        },
        {
          title: ['Contact'],
          p: [
            'お問い合わせ・取材などのご連絡はこちらのメールアドレスまでお願い致します',
            'webmaster@npca.jp'
          ]
        },
        {
          title: ['入部を希望する皆さんへ'],
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
