<template>
  <div class="flex flex-col -space-y-1">
    <button
      @mouseenter="hover = true"
      @mouseleave="hover = false"
      @click="clicked"
      class="bg-green-600 w-32 h-8 rounded-sm"
    >
      array.pop()
    </button>
    <Hover v-if="hover">Remove last element</Hover>
  </div>
</template>

<script>
import Hover from '../../miniComponents/Hover.vue'
export default {
    props: ["arr"],
    data() {
      return {
        hover: false,
      }
    },
    methods: {
        clicked() {
            this.arr.pop();
        },
    },
    components: { Hover }
}
</script>

<style>

</style>