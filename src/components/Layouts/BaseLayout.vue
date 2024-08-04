<script setup lang="ts">
import Headers from './Headers.vue'
import Footers from './Footers.vue'
</script>

<template>
  <main class="bg-white text-gray-500 overflow-x-hidden text-center justify-center items-center">
    <Headers />

    <slot />
  </main>

  <Footers />
</template>
