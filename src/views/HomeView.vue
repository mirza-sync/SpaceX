<script setup lang="ts">
import TimeLine from '@/components/TimeLine.vue'
import { SPACE_X_BASE_URL } from '@/constants'
import type { Launch } from '@/types'
import { useFetch } from '@vueuse/core'

const { data, error, isFetching } = useFetch(`${SPACE_X_BASE_URL}/launches`).get().json<Launch[]>()
</script>

<template>
  <main class="flex w-full">
    <div class="w-1/3 m-auto text-center">
      <h1 class="text-white font-bold text-5xl">Launches</h1>
    </div>
    <div class="w-2/3">
      <div v-if="error">{{ error }}</div>
      <div v-else-if="isFetching">Loading...</div>
      <div v-else class="h-[100dvh] overflow-y-auto">
        <TimeLine :launches="data" />
      </div>
    </div>
  </main>
</template>
