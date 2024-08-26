<script setup lang="ts">
import { SPACE_X_BASE_URL } from '@/constants'
import type { Launch } from '@/types'
import { useFetch } from '@vueuse/core'

const { data, error, isFetching } = useFetch(`${SPACE_X_BASE_URL}/launches`).get().json<Launch[]>()
</script>

<template>
  <main>
    <div v-if="error">{{ error }}</div>
    <div v-else-if="isFetching">Loading...</div>
    <div v-else>
      <pre v-for="launch in data" :key="launch.flight_number">
        {{ new Date(launch.launch_date_unix) }}
      </pre>
    </div>
  </main>
</template>
