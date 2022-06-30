<template>
  <div class="flex flex-col -space-y-1">
    <button
      @mouseenter="hover = true"
      @mouseleave="hover = false"
      @click="clicked"
      class="bg-green-600 w-32 h-8 rounded-sm"
    >
      array.reduce()
    </button>
    <Hover v-if="hover">Ex: array.reduce((acc, val) => acc + val)</Hover>
  </div>
</template>

<script>
import Hover from "../../miniComponents/Hover.vue";

export default {
    props: ["arr"],
    data() {
        return {
            hover: false,
        };
    },
    methods: {
        clicked() {
          if (this.arr.length > 1) {
            for (let i = 1; i < this.arr.length; i++) {
              setTimeout(() => {
                this.arr[1] = this.arr[1] + this.arr[0] 
                this.arr.shift()
              }, i * 1000) 
            }
          }
        },
    },
    components: { Hover }
}
</script>