<template>
  <div class="bg-yellow-100 flex items-center justify-center h-screen pl-64 flex-col space-y-10">
    <p class="text-green-600 transform translate-y-10">array</p>
    <transition-group tag="div" name="fade" class="flex space-x-5 boxes px-8 pt-3 pb-7">
      <div
        v-for="(item, index) in arr"
        :key="item"
        class="h-10 w-10 bg-green-600 flex items-center justify-center rounded-sm relative"
      >
        {{ item }}
        <p class="absolute -bottom-6 text-green-600">{{ index }}</p>
      </div>
    </transition-group>  
    <div class="flex flex-col space-y-10">
      <div class="flex space-x-3">
        <Push :arr="arr" />
        <Pop :arr="arr" />
        <Unshift :arr="arr" />
        <Shift :arr="arr" /> 
      </div>
      <div class="flex space-x-3">
        <Reverse :arr="arr" />
        <Reduce :arr="arr" />
      </div>
    </div>
  </div>
</template>

<script>
import Push from './jsMethods/Push.vue'
import Pop from './jsMethods/Pop.vue';
import Unshift from './jsMethods/Unshift.vue';
import Shift from './jsMethods/Shift.vue';
import Reverse from './jsMethods/Reverse.vue';
import Reduce from './jsMethods/Reduce.vue';

export default {
    data() {
        return {
            arr: [1, 2, 3, 4]
        };
    },
    methods: {
        
        popClicked() {
            this.arr.pop();
        },
        shiftClicked() {
            this.arr.shift();
            this.arr.map((val, index) => {
                if (index > 0) {
                    return val;
                }
            });
        },
        unshiftClicked() {
            if (this.arr.length) {
                this.arr.unshift(this.arr[0] - 1);
            }
            else {
                this.arr.push(0);
            }
        },
    },
    components: { Push, Pop, Unshift, Shift, Reverse, Reduce }
}
</script>

<style>
.fade-move,
.fade-enter-active, 
.fade-leave-active {
  transition: all 1s ease;
}
.fade-enter-from, 
.fade-leave-to {
  opacity: 0;
  transform: scale(0.01);
}
.boxes {
  box-shadow: 
  rgba(0, 0, 0, 0.4) 0px 2px 4px, 
  rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, 
  rgba(0, 0, 0, 0.2) 0px -3px 0px inset;
}
</style>