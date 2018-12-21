<template lang="pug">
  .container
    header
      .header-inner
        .header-logo-container
          img(src="/npca-web/logotype-jp.svg" height="30px")
        ul.nav
          li
            a(href="#") Activities
          li
            a(href="#") Works
    .images
      .image0(v-if="showTopImage[0]")
      .image1(v-if="showTopImage[1]")
      .image2(v-if="showTopImage[2]")
    .title
      h1
        .line.line1
          span H
          span e
          span l
          span l
          span o
        .line.line2
          span W
          span o
          span r
          span l
          span d
          span !
      h2.fi(data-emergence="hidden") 灘校パソコン研究部へようこそ!
    section
      h2.fi(data-emergence="hidden") NPCAとは?
      p.fi(data-emergence="hidden") NPCA: 灘校パソコン研究部は、灘中学校・高等学校の部活動の1つです
      p.fi(data-emergence="hidden") 普段から幅広く活動しています
      p.fi(data-emergence="hidden") 部会以外での招集はなく、自由なスタイルの部活です
      separator
      h2.fi(data-emergence="hidden") NPCAの由来
      p.fi(data-emergence="hidden") Nada Personal Computer users' Association
      p.fi(data-emergence="hidden") 直訳すると "灘校パソコン使用者の会" の頭文字を取った愛称です
      p.fi(data-emergence="hidden") users'のuが入らないのは、考案者が語感を重視したためだと言われています
      p.fi(data-emergence="hidden") 大文字・小文字は特に区別しません
      separator
      h2.fi(data-emergence="hidden") Contact
      p.fi(data-emergence="hidden") お問い合わせ・取材などのご連絡はこちらのメールアドレスにお願いいたします
      p.fi(data-emergence="hidden") webmaster@npca.jp
      separator
      h2.fi(data-emergence="hidden") 入部希望者の皆さんへ
      p.fi(data-emergence="hidden") NPCAは常時入部を受け付けています
      p.fi(data-emergence="hidden") 東館2階視聴覚室の向かいの部室まで、気軽にお越しください!
      p.fi(data-emergence="hidden") 扉に貼られたNPCAロゴが目印です
    footer
</template>

<script>
import anime from 'animejs'
import emergence from 'emergence.js'
import separator from '~/components/separator.vue'
window.onload = function() {
  const h1 = document.querySelector('.title h1')
  h1.style.opacity = 1
  ;(this.anime1 = anime.timeline({}).add({
    targets: '.line1 span',
    translateY: ['1.2em', 0],
    duration: 500,
    delay: function(el, i) {
      return 50 * i + 500
    },
    easing: 'easeOutQuart'
  })),
    (this.anime2 = anime.timeline({}).add({
      targets: '.line2 span',
      translateY: ['1.2em', 0],
      duration: 500,
      delay: function(el, i) {
        return 50 * i + 700
      },
      easing: 'easeOutQuart'
    }))
}
export default {
  components: { separator },
  data() {
    return {
      topImage: 0,
      showTopImage: [true, false, false],
      anime1: '',
      anime2: '',
      showTitle: false
    }
  },
  mounted() {
    emergence.init({
      reset: false
    })
  }
}
</script>

<style lang="stylus">
.container
  min-height: 100vh;
  
.fi[data-emergence=hidden]
  transform translateY(70px)
  opacity 0
.fi[data-emergence=visible]
  opacity 1
  transition all 700ms
  
header
  display block
  height 80px
  position relative

  .header-inner
    height 100%
    margin 0 20px
    display flex
    align-items center
    justify-content space-between
    .header-logo-container
      z-index 2
      a
        width 100%
        height 100%
    .nav
      height 100%
      display flex
      align-items center
      justify-content space-around
      z-index 2
      li
        margin 0 10px
        list-style none
      a
        transition all .3s
        color #000
        font-weight 600
        padding 10px 20px
        border-radius 20px
        background-color #fff
        box-shadow 0px 0px 10px 2px rgba(255, 255, 255, 0.3)
        &:hover
          transition all .3s
          color rgba(0, 0, 0, 0.8)
          box-shadow 0px 2px 5px 5px rgba(255, 255, 255, 0.3)
          
.images
  background-color #000
  height 70vh
  width 100%
  margin-top -80px
  position absolute
  .image0
  .image1
  .image2
    height 100%
    opacity .85
    background-size cover
    background-blend-mode color
.image0
  background-image linear-gradient(to right top, #0f42c2, #0077e9, #009edf, #00beb3, #1ed87f), url(/npca-web/img/top-0.jpg)
.image1
  background-image linear-gradient(to right top, #0f42c2, #0077e9, #009edf, #00beb3, #1ed87f), url(/npca-web/img/top-1.jpg)
.image2
  background-image linear-gradient(to right top, #0f42c2, #0077e9, #009edf, #00beb3, #1ed87f), url(/npca-web/img/top-2.jpg)

.title
  width 800px
  height 70vh
  margin -80px auto 0
  display flex
  flex-direction column
  align-items flex-start
  justify-content center
  color #fff
  *
    z-index 1
  h1
    font-size 90pt
    font-weight 700
    opacity 0
    .line
      overflow hidden
      margin -20px 0
      span
        display inline-block
        margin-right 15px
  h2
    margin-top 32pt
    font-size 30px
    font-family 'Noto Sans JP'
    font-weight 700
    
section
  width 800px
  margin 0 auto
  h2
    margin 100px 0 50px
    font-size 32pt
  p
    margin 20px 0
    
footer
  width 100%
  height 300px
  margin-top 100px
  background-color #000
</style>
