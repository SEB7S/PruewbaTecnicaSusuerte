<template>
  <div>
    <table class="table table-light table-striped table-hover">
      <thead>
        <tr>
          <th scope="col">Nombre Completo</th>
          <th scope="col">Género</th>
          <th scope="col">País</th>
          <th scope="col">Email</th>
          <th scope="col">Telefono</th>
        </tr>
      </thead>
      <tbody>
          <!-- Recorriendo Array de forma dinamica -->
        <tr v-for="(user, index) in aUsers" :key="index">
          <td>{{ user.name["first"] }} {{ user.name["last"] }}</td>
          <td>{{ user.gender }}</td>
          <td>{{ user.location["country"] }}</td>
          <td>{{ user.email }}</td>
          <td>{{ user.phone }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
/* Libreria para realizar peticiones */
import axios from "axios";
/* Libreria para realizar peticiones */

const initialData = () => ({
  /* Variables */
  /* Array para almacenar usuarios */
  aUsers: [],
  /* Array para almacenar usuarios */
});
export default {
  name: "UserComponent",
  data: function () {
    return initialData();
  },
  methods: {
    /* Obteniendo usuarios con axios */
    getUser() {
      console.log("Cola");
      axios
        .get("https://randomuser.me/api/", {})
        .then((response) => {
          console.log(response.data.results[0]);
          this.aUsers = response.data.results;

          /* Esta ciclo lo utilice con el fin de simular los datos que me retorna la peticion ya que en este momento solo me retorna uno */
          for (let index = 0; index < 5; index++) {
            this.aUsers.push(response.data.results[0]);
          }
        })
        .catch((error) => {
          /* Capturando errores  */
          console.error("no se pudo realizar la peticion", error);
        });
    },
  },
  mounted() {
    /* Ejecutando metodo de listar usuario  */
    this.getUser();
  },
};
</script>
<style>
</style>
