<template>
  <div class="flex flex-col -space-y-1">
    <button
      @mouseenter="hover = true"
      @mouseleave="hover = false"
      @click="clicked"
      class="bg-green-600 px-8 py-1 rounded-sm"
    >
      array.unshift({{ arr[0] - 1 || 0 }})
    </button>
    <Hover v-if="hover">Add element to the beginning</Hover>
  </div>
</template>

<script>
import Hover from "../../miniComponents/Hover.vue";

export default {
  props: ['arr'],
  data() {
    return {
      hover: false
    }
  },
  methods: {
    clicked() {
      if (this.arr.length) {
        this.arr.unshift(this.arr[0] - 1);
      }
      else {
        this.arr.push(0);
      }
    },
  },
  components: { Hover },
}
</script>