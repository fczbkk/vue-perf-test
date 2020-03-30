<template functional>
  <div>
    <component :is="injections.components.ChildComponent" />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent'
export default {
  inject: {
    components: {
      default: {
        ChildComponent
      }
    }
  }
}
</script>

<style scoped>

</style>
