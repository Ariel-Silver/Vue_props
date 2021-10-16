<template>
  <div id="App" class="text-center">
    <h1 class="py-3">Crear una nueva tarea</h1>
    <label class="pr-4">Tarea</label>
    <input class="me-4 ms-4" type="text" v-model="Deberes" placeholder="Ingrese nueva tarea"/>
    <button class="btn btn-dark btn-lg" @click="Agregar">Agregar</button>
    <componente
      :Tareas="Tareas"
      @eliminardeLista="eliminardeLista"
    ></componente>
  </div>
</template>

<script>
import componente from "./components/componentes.vue";

export default {
  name: "App",
  components: { componente },
  data: () => ({
    Deberes: "",
    Tareas: ["Limpiar arenero de la gata", "botar la basura"],
  }),
  methods:{
    Agregar: function(){
      this.Tareas.push(this.Deberes)
      this.Deberes = "";
    },
    eliminardeLista: function (index) {
      this.Tareas.splice(index, 1);
      },
  },
};
</script>

<style scoped>
body,html {
  width: 100%;
  height: 100%;
}

p {
  margin-top: 20px;
  margin-right: 20px;
  font-size: large;
  text-decoration: underline;
}

button {
  margin-top: 30px;
  width: 150px;
  height: 45px;
  padding-top: 1px;
} 

input {
  width: 500px;
  border: solid 1px black;
}
label {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-weight: 600;
  font-size: 30px;
}

ul {
  font-weight:bold;
}

li {
  margin-right: 20px;
}
</style>
