<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useI18n } from 'vue-i18n'
import LangSwitcher from '../components/LangSwitcher.vue'

const { t } = useI18n()
const router = useRouter()
const name = ref('')
const email = ref('')
const password = ref('')
const confirmPassword = ref('')

function handleRegister() {
  // ponytail: no auth logic, just navigate
  router.push('/dashboard')
}
</script>

<template>
  <div class="auth-container">
    <LangSwitcher />
    <div class="auth-card">
      <div class="auth-header">
        <h1>{{ t('register.title') }}</h1>
        <p>{{ t('register.subtitle') }}</p>
      </div>
      <form class="auth-form" @submit.prevent="handleRegister">
        <div class="field">
          <label for="name">{{ t('register.name') }}</label>
          <input id="name" v-model="name" type="text" :placeholder="t('register.namePlaceholder')" required />
        </div>
        <div class="field">
          <label for="email">{{ t('register.email') }}</label>
          <input id="email" v-model="email" type="email" :placeholder="t('register.emailPlaceholder')" required />
        </div>
        <div class="field">
          <label for="password">{{ t('register.password') }}</label>
          <input id="password" v-model="password" type="password" :placeholder="t('register.passwordPlaceholder')" required />
        </div>
        <div class="field">
          <label for="confirmPassword">{{ t('register.confirmPassword') }}</label>
          <input id="confirmPassword" v-model="confirmPassword" type="password" :placeholder="t('register.passwordPlaceholder')" required />
        </div>
        <button type="submit" class="btn-primary">{{ t('register.submit') }}</button>
      </form>
      <p class="auth-footer">
        {{ t('register.hasAccount') }}
        <router-link to="/login">{{ t('register.signIn') }}</router-link>
      </p>
    </div>
  </div>
</template>
