<script setup lang="ts">
import { useI18n } from 'vue-i18n'

const { locale } = useI18n()

const languages = [
  { code: 'en', label: 'English' },
  { code: 'pt', label: 'Portugues' },
]
</script>

<template>
  <select class="lang-switcher" v-model="locale">
    <option v-for="lang in languages" :key="lang.code" :value="lang.code">
      {{ lang.label }}
    </option>
  </select>
</template>
