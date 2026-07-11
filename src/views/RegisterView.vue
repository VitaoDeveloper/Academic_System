<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

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
    <div class="auth-card">
      <div class="auth-header">
        <h1>Create account</h1>
        <p>Get started for free</p>
      </div>
      <form class="auth-form" @submit.prevent="handleRegister">
        <div class="field">
          <label for="name">Full name</label>
          <input id="name" v-model="name" type="text" placeholder="John Doe" required />
        </div>
        <div class="field">
          <label for="email">Email</label>
          <input id="email" v-model="email" type="email" placeholder="you@example.com" required />
        </div>
        <div class="field">
          <label for="password">Password</label>
          <input id="password" v-model="password" type="password" placeholder="••••••••" required />
        </div>
        <div class="field">
          <label for="confirmPassword">Confirm password</label>
          <input id="confirmPassword" v-model="confirmPassword" type="password" placeholder="••••••••" required />
        </div>
        <button type="submit" class="btn-primary">Create account</button>
      </form>
      <p class="auth-footer">
        Already have an account?
        <router-link to="/login">Sign in</router-link>
      </p>
    </div>
  </div>
</template>
