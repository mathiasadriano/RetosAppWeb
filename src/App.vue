<template>
  <div id="app">
    <auth-page />
  </div>
</template>

<script>
import AuthPage from '@/components/AuthPage.vue';

export default {
  name: 'App',
  components: {
    AuthPage,
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  color: #333; /* Color de texto oscuro para todo el documento */
  margin: 0;
  padding: 0;
  height: 100vh; /* Ocupa toda la altura de la ventana */
  display: flex;
  align-items: center;
  justify-content: center;
}

#app {
  width: 100%; /* Asegura que el contenedor ocupe toda la ventana */
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
