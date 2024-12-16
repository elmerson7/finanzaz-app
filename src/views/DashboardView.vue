<template>
  <div>
    <h1 v-if="isAuthenticated">Bienvenido al Dashboard</h1>
    <LoginView v-else />
    <!-- Si no está autenticado, muestra el Login en la misma URL -->
  </div>
</template>

<script lang="ts">
import { useAuthStore } from '@/stores/auth'
import LoginView from './LoginView.vue'

export default {
  components: { LoginView },
  setup() {
    const authStore = useAuthStore()
    return {
      isAuthenticated: authStore.isAuthenticated,
    }
  },
}
</script>
