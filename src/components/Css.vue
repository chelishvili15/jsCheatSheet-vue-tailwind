<script setup>
import Header from './Header.vue'
</script>

<template>
  <div>
    <Header :titles="array" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      array: [
        'Something',
        'SomeThing',
        'Some',
        'Someone'
      ]
    }
  }
}
</script>

<style>

</style>