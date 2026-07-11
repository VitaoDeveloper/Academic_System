<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
const router = useRouter()
const email = ref('')
const role = ref('aluno')
const password = ref('')

function handleLogin() {
  // ponytail: no auth logic, just navigate
  router.push('/dashboard')
}
</script>

<template>
  <div class="auth-container">
    <div class="auth-card">
      <div class="auth-header">
        <h1>{{ t('login.title') }}</h1>
        <p>{{ t('login.subtitle') }}</p>
      </div>
      <form class="auth-form" @submit.prevent="handleLogin">
        <div class="field">
          <label for="role"></label>
          <select id="role" v-model="role" required>
            <option value="aluno">{{ t('login.roles.aluno') }}</option>
            <option value="professor">{{ t('login.roles.professor') }}</option>
            <option value="coordenador">{{ t('login.roles.coordenador') }}</option>
            <option value="administrador">{{ t('login.roles.administrador') }}</option>
          </select>
        </div>
        <div class="field">
          <label for="email">{{ t('login.email') }}</label>
          <input id="email" v-model="email" type="email" :placeholder="t('login.emailPlaceholder')" required />
        </div>
        <div class="field">
          <label for="password">{{ t('login.password') }}</label>
          <input id="password" v-model="password" type="password" :placeholder="t('login.passwordPlaceholder')" required />
        </div>
        <button type="submit" class="btn-primary">{{ t('login.submit') }}</button>
      </form>
      <p class="auth-footer">
        {{ t('login.noAccount') }}
        <router-link to="/register">{{ t('login.createAccount') }}</router-link>
      </p>
    </div>
  </div>
</template>
