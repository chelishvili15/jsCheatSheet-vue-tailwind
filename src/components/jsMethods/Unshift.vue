<template>
  <div class="flex flex-col -space-y-1">
    <button
      @mouseenter="hover = true"
      @mouseleave="hover = false"
      @click="clicked"
      class="bg-green-600 w-32 h-8 rounded-sm"
    >
      array.unshift({{ getValue || 0 }})
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
          const length = this.arr.length
          if (length > 0 && this.arr[1] < this.arr[0]) {
            this.arr.unshift(this.arr[0] + 1)
          } else {
            this.arr.unshift(this.arr[0] - 1)
          }
        }
      else {
        this.arr.push(0);
      }
    },
  },
  computed: {
      getValue() {
        if (this.arr.length) {
          if (this.arr.length > 0) {
            if (this.arr[1] < this.arr[0]) {
              return this.arr[0] + 1 
            }
            return this.arr[0] - 1
          }
        }
      },
    },
  components: { Hover },
}
</script>