<script setup lang="ts">
import type { Launch } from '@/types'
defineProps<{
  launches: Launch[] | null
}>()
</script>

<template>
  <div class="flex flex-col gap-4 p-4">
    <div v-for="launch of launches" :key="launch.flight_number">
      <!-- Card -->
      <div class="bg-white p-4 rounded border border-slate-200 shadow text-black">
        <h2>{{ launch.mission_name }}</h2>
        <span>{{ launch.launch_date_local }}</span>
        <div>{{ launch.details }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
