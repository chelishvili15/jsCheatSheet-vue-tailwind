<template>
  <div class="bg-yellow-100 flex items-center justify-center h-screen pl-64 flex-col space-y-10">
    <p class="text-green-600 transform translate-y-10">array</p>
    <transition-group class="flex space-x-5 boxes px-8 py-3" name="boxes" tag="div">
      <div
        v-for="(box,index) in arr"
        :key="index"
        class="h-10 w-10 bg-green-600 flex items-center justify-center rounded-sm"
      >
        {{ box }}
      </div>
    </transition-group>  
    <div class="flex space-x-3">
        <button @click="pushClicked" class="bg-green-600 px-8 py-1 rounded-sm">
          array.push({{ arr[arr.length - 1] + 1 || 0 }})
        </button>
        <button @click="popClicked" class="bg-green-600 px-8 py-1 rounded-sm">
          array.pop()
        </button>
        <button @click="shiftClicked" class="bg-green-600 px-8 py-1 rounded-sm">
          array.shift()
        </button>
        <button @click="unshiftClicked" class="bg-green-600 px-8 py-1 rounded-sm">
          array.unshift({{ arr[0] - 1 || 0}})
        </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1,2,3,4]
    }
  },
  methods: {
    pushClicked() {
      if (this.arr.length) {
        this.arr.push(this.arr[this.arr.length - 1] + 1)
      } else {
        this.arr.push(0)
      }
    },
    popClicked() {
      this.arr.pop()
    },
    shiftClicked() {
      this.arr.shift()
      this.arr.map((val, index) => {
        if (index > 0) {
          return val
        }
      })
    },
    unshiftClicked() {
      if (this.arr.length) {
        this.arr.unshift(this.arr[0] - 1)
      } else {
        this.arr.push(0)
      }
    },
  },
}
</script>

<style>
.boxes-enter-active, .boxes-leave-active {
  transition: all 1s ease;
}
.boxes-enter-from, .boxes-leave-to {
  opacity: 0.1;
  transform: translateX(20px);
}
.boxes {
  box-shadow: 
  rgba(0, 0, 0, 0.4) 0px 2px 4px, 
  rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, 
  rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
}
</style>