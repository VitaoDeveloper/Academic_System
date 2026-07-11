<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import LangSwitcher from '../components/LangSwitcher.vue'

const { t } = useI18n()
</script>

<template>
  <div class="dashboard">
    <nav class="dashboard-nav">
      <span class="brand">{{ t('brand') }}</span>
      <div class="nav-right">
        <LangSwitcher />
        <router-link to="/login" class="btn-ghost">{{ t('dashboard.logout') }}</router-link>
      </div>
    </nav>
    <main class="dashboard-content">
      <h1>{{ t('dashboard.title') }}</h1>
      <p>{{ t('dashboard.welcome') }}</p>
    </main>
  </div>
</template>
