<template>
  <div>
    <div v-if="showContent">
      <FunctionalComponent v-for="(item, index) of items" :key="index" />
    </div>
  </div>
</template>

<script>
import FunctionalComponent from './FunctionalComponent'
export default {
  components: {
    FunctionalComponent
  },
  data () {
    return {
      showContent: false,
      items: new Array(100000)
    }
  },
  mounted () {
    this.showContent = true
  },

  beforeUpdate () {
    // eslint-disable-next-line
    console.time('perf')
  },

  updated () {
    // eslint-disable-next-line
    console.timeEnd('perf')
  }
}
</script>

<style scoped>

</style>
