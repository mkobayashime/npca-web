<template lang="pug">
	.npSetionTitle.fi.fi-up(data-emergence="hidden")
		.line
			span(v-for="c in getText") {{c}}
</template>

<script>
import anime from 'animejs'
export default {
  name: 'NpSetionTitle',
  props: {
    text: {
      type: String,
      default: function() {
        return 'This is Title'
      }
    }
  },
  computed: {
    getText: function() {
      return this.text.split('')
    }
  },
  mounted() {
    this.anime = anime({
      targets: '.NpSectionTitle span',
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
.line
	font-size 40px
	overflow hidden
	span
		margin 0 2px 0 0
		display inline-block
</style>
