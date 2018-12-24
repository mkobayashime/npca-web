<template lang="pug">
	.NpPageTitle
		.line
			span(v-for="c in getText") {{c}}
</template>

<script>
import anime from 'animejs'
export default {
  name: 'NpPageTitle',
  props: {
    text: {
      type: String,
      default: function() {
        return 'Title'
      }
    }
  },
  data() {
    return {
      an: 'ABC'
    }
  },
  computed: {
    getText: function() {
      return this.text.split('')
    }
  },
  mounted() {
    this.anime = anime({
      targets: '.line span',
      translateY: ['1.2em', 0],
      duration: 500,
      delay: function(el, i) {
        return 50 * i + 200
      },
      easing: 'easeOutQuart'
    })
  }
}
</script>

<style lang="stylus" scoped>
.NpPageTitle
  width 800px
  color #000
	.line
		font-size 100px
		font-weight 700
		margin 0
		overflow hidden
		span
			overflow hidden
			margin 0
			display inline-block
			margin-right 15px
</style>
