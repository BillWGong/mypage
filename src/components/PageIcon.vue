<script setup>
defineProps({ name: { type: String, required: true } })

const paths = {
  sun: ['M12 8a4 4 0 1 0 0 8 4 4 0 0 0 0-8', 'M12 2v2m0 16v2M2 12h2m16 0h2M4.93 4.93l1.42 1.42m11.3 11.3 1.42 1.42M4.93 19.07l1.42-1.42m11.3-11.3 1.42-1.42'],
  moon: ['M20.9 13.1A9 9 0 0 1 10.9 3.1a9 9 0 1 0 10 10Z'],
  system: ['M4 4h16a1 1 0 0 1 1 1v11a1 1 0 0 1-1 1H4a1 1 0 0 1-1-1V5a1 1 0 0 1 1-1Z', 'M8 21h8m-4-4v4'],
  external: ['M7 17 17 7M7 7h10v10'],
}
</script>

<template>
  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
    <path v-for="(path, index) in paths[name] || []" :key="index" :d="path" />
  </svg>
</template>
