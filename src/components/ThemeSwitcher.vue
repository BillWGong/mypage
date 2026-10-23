<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import PageIcon from './PageIcon.vue'

const preference = ref('system')
const choices = [
  { value: 'light', icon: 'sun', label: 'Light theme' },
  { value: 'dark', icon: 'moon', label: 'Dark theme' },
  { value: 'system', icon: 'system', label: 'Use system theme' },
]
let media

function applyTheme() {
  const theme = preference.value === 'system'
    ? media?.matches ? 'dark' : 'light'
    : preference.value
  document.documentElement.dataset.theme = theme
  document.querySelector('meta[name="theme-color"]')?.setAttribute('content', theme === 'dark' ? '#171816' : '#fbfaf8')
}

function setTheme(value) {
  preference.value = value
  try { localStorage.setItem('billw-theme', value) } catch {}
  applyTheme()
}

onMounted(() => {
  media = window.matchMedia('(prefers-color-scheme: dark)')
  try {
    const saved = localStorage.getItem('billw-theme')
    if (choices.some(choice => choice.value === saved)) preference.value = saved
  } catch {}
  media.addEventListener('change', applyTheme)
  applyTheme()
})

onUnmounted(() => media?.removeEventListener('change', applyTheme))
</script>

<template>
  <div class="theme-switcher" role="group" aria-label="Color theme">
    <button v-for="choice in choices" :key="choice.value" type="button" :aria-label="choice.label" :title="choice.label" :aria-pressed="preference === choice.value" @click="setTheme(choice.value)">
      <PageIcon :name="choice.icon" />
    </button>
  </div>
</template>
