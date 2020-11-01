<template>
  <button class="font-bold py-2 px-4 rounded mr-2 bg-gray-700 text-white">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "base-button",
  props: ['text']
}
</script>

<style scoped>
.btn {
  @apply font-bold py-2 px-4 rounded mr-2;
}
.btn-blue {
  @apply bg-gray-700 text-white;
}
.btn-blue:hover {
  @apply bg-gray-800;
}
</style>
