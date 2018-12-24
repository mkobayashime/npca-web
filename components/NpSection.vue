<template lang="pug">
  .npSectionContainer
    h2.fi.fi-up(data-emergence="hidden") {{section.title}}
    .textContainer(v-for="p in section.p")
      p.fi.fi-up(data-emergence="hidden") {{p}}
</template>

<script>
import emergence from 'emergence.js'
export default {
  name: 'NpSection',
  props: {
    section: {
      type: Object,
      default: function() {
        return {
          title: 'This is Title',
          p: ['This is text']
        }
      }
    }
  },
  data() {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
h2
  margin 100px 0 50px
  font-size 40px
p
  margin 20px 0
  font-size 16px
</style>
