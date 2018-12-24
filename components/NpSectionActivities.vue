<template lang="pug">
  .npSectionContainer
    h2
      np-section-title(:text="text" :key="index" v-for="text in section.year")
    np-activitie-line(:ps="section.ps")
</template>

<script>
import emergence from 'emergence.js'
import NpActivitieLine from '~/components/NpActivitieLine.vue'
import NpSectionTitle from '~/components/NpSectionTitle.vue'
export default {
  name: 'NpSection',
  components: { NpActivitieLine, NpSectionTitle },
  props: {
    section: {
      type: Object,
      default: function() {
        return {
          yaer: ['20xx'],
          ps: [
            {
              date: 'xx.xx - xx.xx',
              text: 'text',
              links: [['label', 'url']]
            }
          ]
        }
      }
    }
  },
  computed: {
    getLink() {
      return this.section.ps.link
    }
  }
}
</script>

<style lang="stylus" scoped>
h2
  margin 100px 0 50px
  font-size 40px
</style>
