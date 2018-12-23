<template lang="pug">
  .npSectionContainer
    np-separator
    h2.fi.fi-up(data-emergence="hidden") {{section.year}}
    np-activitie-line(:ps="section.ps")
</template>

<script>
import emergence from 'emergence.js'
import NpActivitieLine from '~/components/NpActivitieLine.vue'
import NpButtonS from '~/components/NpButtonS.vue'
import NpSeparator from '~/components/NpSeparator.vue'
export default {
  name: 'NpSection',
  components: { NpActivitieLine, NpButtonS, NpSeparator },
  props: {
    section: {
      type: Object,
      default: function() {
        return {
          yaer: '20xx'
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
