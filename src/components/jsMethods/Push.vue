<template>
  <div class="flex flex-col -space-y-1">
    <button
      @mouseenter="hover = true"
      @mouseleave="hover = false"
      @click="clicked"
      class="bg-green-600 w-32 h-8 rounded-sm"
    >
      array.push({{ getValue || 0 }})
    </button>
    <Hover v-if="hover">Add element at last</Hover>
  </div>
</template>

<script>
import Hover from '../../miniComponents/Hover.vue';

export default {
    props: ["arr"],
    data() {
      return {
        hover: false,
        value: 5,
      }
    },
    methods: {
      clicked() {
        if (this.arr.length) {
          const length = this.arr.length
          if (length > 0 && this.arr[length - 1] < this.arr[length-2]) {
            this.arr.push(this.arr[length - 1] - 1)
          } else {
            this.arr.push(this.arr[length - 1] + 1)
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
            if (this.arr[this.arr.length - 1] < this.arr[this.arr.length - 2]) {
              return this.arr[this.arr.length - 1] - 1 
            }
            return this.arr[this.arr.length - 1] + 1
          }
        }
      },
    },
    components: { Hover }
}
</script>

<style>

</style>