<template>
  <div class="auth-page">
    <div class="toggle-buttons">
      <button @click="isLogin = true" :disabled="isLogin">Ir a Login</button>
      <button @click="isLogin = false" :disabled="!isLogin">Ir a Registro</button>
    </div>
    <login-form v-if="isLogin"></login-form>
    <register-form v-else></register-form>
  </div>
</template>

<script>
import LoginForm from '@/components/LoginForm.vue';
import RegisterForm from '@/components/RegisterForm.vue';

export default {
  name: 'AuthPage',
  components: {
    LoginForm,
    RegisterForm,
  },
  data() {
    return {
      isLogin: true, // Estado inicial para mostrar el formulario de login
    };
  },
};
</script>

<style scoped>
.auth-page {
  display: flex;
  flex-direction: column;
  align-items: center; /* Centra horizontalmente */
  justify-content: center; /* Centra verticalmente */
  height: 100vh; /* Ocupa toda la altura de la ventana */
  max-width: 500px;
  margin: auto;
  text-align: center;
  color: #333; /* Color de texto oscuro para toda la página de autenticación */
}

.toggle-buttons {
  margin-bottom: 20px;
}

button {
  padding: 10px 15px;
  margin: 5px;
  background-color: #6c757d;
  color: #fff; /* Texto blanco para contraste */
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background-color: #ccc; /* Botones deshabilitados más claros */
}

button:hover:not(:disabled) {
  background-color: #5a6268;
}
</style>
