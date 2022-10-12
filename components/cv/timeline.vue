<template>
    <div>
        <v-timeline dense>
            <timelineItem
                v-for="(item, i) in cv"
                :key="i"
                :experience="item"
            />
        </v-timeline>
    </div>
  </template>

<script>
import timelineItem from './timelineItem.vue'

export default {
    name: 'timeline',

    props: {
        cv: Array
    },

    components: {
        timelineItem
    }
}
</script>

<style lang="css" scopped>
  .v-timeline::before {
      top: 55px;
      height: calc(100% - 110px)
  }
</style>