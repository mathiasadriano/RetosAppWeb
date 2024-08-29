<template>
  <div class="register-form">
    <h2>Registrarse</h2>
    <form @submit.prevent="handleRegister">
      <div class="form-group">
        <label for="username">Nombre de Usuario:</label>
        <input type="text" id="username" v-model="username" required />
      </div>
      <div class="form-group">
        <label for="email">Correo Electrónico:</label>
        <input type="email" id="email" v-model="email" required />
      </div>
      <div class="form-group">
        <label for="password">Contraseña:</label>
        <input type="password" id="password" v-model="password" required />
      </div>
      <div class="form-group">
        <label for="confirmPassword">Confirmar Contraseña:</label>
        <input type="password" id="confirmPassword" v-model="confirmPassword" required />
      </div>
      <div class="form-group">
        <label for="userType">Tipo de Usuario:</label>
        <select id="userType" v-model="userType">
          <option v-for="(label, type) in userTypes" :key="type" :value="type">
            {{ label }}
          </option>
        </select>
      </div>
      <button type="submit">Registrarse</button>
    </form>
  </div>
</template>

<script>
import { USER_TYPES } from '@/constants';

export default {
  name: 'RegisterForm',
  data() {
    return {
      username: '',
      email: '',
      password: '',
      confirmPassword: '',
      userType: USER_TYPES.USER,
    };
  },
  computed: {
    userTypes() {
      return USER_TYPES;
    },
  },
  methods: {
    handleRegister() {
      console.log('Registering:', {
        username: this.username,
        email: this.email,
        userType: this.userType,
      });
    },
  },
};
</script>

<style scoped>
.register-form {
  color: #333; /* Color de texto oscuro para mejor contraste */
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  color: #333; /* Color de texto oscuro */
}

input,
select {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
}

button {
  padding: 10px 15px;
  background-color: #28a745;
  color: #fff; /* Texto blanco para contraste con el botón */
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #218838;
}
</style>
