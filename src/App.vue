<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="flex flex-col h-[100dvh]">
    <header class="p-4">
      <div class="text-xl">Hello Space X</div>
    </header>
    <div class="flex-grow overflow-hidden">
      <RouterView />
    </div>
  </div>
</template>

<style scoped></style>
