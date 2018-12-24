<template lang="pug">
  .lineContainer
    .line(v-for="p in ps")
      .date.fi.fi-up(data-emergence="hidden") {{p.date}}
      .textContainer
        .text.fi.fi-up(data-emergence="hidden") {{p.text}}
        .linkContainer(v-for="link in p.links")
          a(:href="link[1]" target="_blank" v-if="!link[2]")
            np-button-s {{link[0]}}
          nuxt-link(:to="link[1]" v-if="link[2]")
            np-button-s {{link[0]}}
</template>

<script>
import NpButtonS from '~/components/NpButtonS.vue'
export default {
  name: 'NpActivitieLine',
  components: { NpButtonS },
  props: {
    ps: {
      type: Array,
      default: function() {
        return {
          date: 'xx.xx - xx.xx',
          text: 'text',
          links: ['link label', 'link', false]
        }
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.line
  display flex
  margin 30px 0
  .date
    width 200px
    font-size 26px
    font-weight 700
  .textContainer
    display flex
    flex-wrap wrap
    width 600px
    .text
      width 600px
      margin-bottom 10px
      line-height 2em
  .linkContainer
    display flex
</style>
