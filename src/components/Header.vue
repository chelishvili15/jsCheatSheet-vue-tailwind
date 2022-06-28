<template>
  <div class="fixed bg-green-600 h-28 w-full flex items-center justify-center shadow-sm space-x-10 pl-64 text-green-600">
    <h1
      v-for="(title, index) in titles"
      :key="index"
      class="cursor-pointer bg-yellow-100 px-10 py-2 rounded-sm hover:scale-125 transform duration-300"
    >
      {{ title }}
    </h1>
  </div>
</template>

<script>
export default {
  props: ['titles'],
}
</script>