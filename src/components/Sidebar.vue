<script setup>
import Buttons from '../miniComponents/SidebarButtons.vue'
</script>

<template>
  <div class="fixed bg-green-600 w-64 h-screen flex items-center justify-center shadow-sm flex-col">
    <buttons @click="htmlClicked"> HTML </buttons>
    <buttons @click="cssClicked"> CSS </buttons>
    <buttons @click="jsClicked"> JavaScript </buttons>
  </div>
</template>

<script>
export default {
  methods: {
    htmlClicked() {
      this.$emit('htmlClicked')
    },
    cssClicked() {
      this.$emit('cssClicked')
    },
    jsClicked() {
      this.$emit('jsClicked')
    },
  }
}
</script>