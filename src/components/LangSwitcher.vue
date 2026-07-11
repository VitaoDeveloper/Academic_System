<script setup lang="ts">
import { useI18n } from 'vue-i18n'

const { locale } = useI18n()

function toggle() {
  locale.value = locale.value === 'en' ? 'pt' : 'en'
}
</script>

<template>
  <button class="lang-switcher" @click="toggle">
    {{ locale === 'en' ? 'PT' : 'EN' }}
  </button>
</template>
