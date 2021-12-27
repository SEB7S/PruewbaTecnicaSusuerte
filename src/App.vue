<template>
  <div id="app">
    <!-- NavBar que busca mostrar un encabezado en la pagina -->
    <ProfileComponent />
    <!-- NavBar que busca mostrar un encabezado en la pagina -->

    <div class="d-flex align-items-center flex-column mt-5">
      <h3 class="text-white text-start">Prueba técnica</h3>
      <p class="text-white w-50">
        A continuación encontrará la información de un servicio web que retorna
        la información de un usuario aleatoriamente. Consuma el servicio web y
        liste en una tabla la siguiente información de 5 usuarios:
      </p>
      <ul class="text-white">
        <li>Nombre completo</li>
        <li>Género</li>
        <li>País</li>
        <li>Email</li>
        <li>Teléfono</li>
      </ul>
      <!-- Componente utilizado para cargar la tabla con sus respectivos usuarios -->
      <UserComponent />
      <!-- Componente utilizado para cargar la tabla con sus respectivos usuarios -->
    </div>
  </div>
</template>

<script>
/* Importando Componentes */
import UserComponent from "./components/UserComponent.vue";
import ProfileComponent from "./components/ProfileComponent.vue";
/* Importando Componentes */
export default {
  name: "App",
  components: {
    UserComponent,
    ProfileComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
