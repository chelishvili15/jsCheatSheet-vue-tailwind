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
        'TAGS',
        'ATTR',
        'EVENTS',
      ]
    }
  }
}
</script>

<style>

</style>