<template>
  <div class="fixed inset-0 z-50 flex items-center justify-center">
    <div class="absolute inset-0 bg-black/50" @click="$emit('close')"></div>
    <div class="relative bg-white rounded-lg max-w-3xl lg:max-w-5xl w-full mx-4 p-6 lg:p-8 shadow-lg lg:h-auto max-h-[90vh] overflow-y-auto">
      <button class="absolute top-3 right-3 text-gray-500 hover:text-gray-700" @click="$emit('close')">✕</button>
      <h3 class="text-xl font-semibold mb-4 text-sky-800">{{ title }}</h3>
      <div class="modal-content">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{ title?: string }>()
</script>

<style scoped>
.modal-content img { border-radius: 0.5rem; }
</style>
