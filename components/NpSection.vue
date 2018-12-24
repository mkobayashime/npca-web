<template lang="pug">
  .npSectionContainer
    h2
      np-section-title(:text="text" :key="index" v-for="text in section.title")
    .textContainer(v-for="p in section.p")
      p.fi.fi-up(data-emergence="hidden") {{p}}
</template>

<script>
import emergence from 'emergence.js'
import NpSectionTitle from '~/components/NpSectionTitle.vue'
export default {
  name: 'NpSection',
  components: { NpSectionTitle },
  props: {
    section: {
      type: Object,
      default: function() {
        return {
          title: ['This is Title'],
          p: ['This is text']
        }
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
h2
  margin 100px 0 50px
p
  margin 20px 0
  font-size 16px
</style>
