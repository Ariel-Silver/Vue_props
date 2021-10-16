<template>
  <div class="componente">
    <ul class="list">
        <p>To Do:</p>
      <li v-for="(Tarea, index) of Tareas" :key="index">
        {{ index }}. {{ Tarea }}
        <button @click="eliminardeLista(index)">Eliminar</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "componente",
  props: {
    Tareas: {
      type: Array,
    },
  },
  methods: {
    eliminardeLista(index) {
      this.$emit("eliminardeLista", index);
    },
  },
};
</script>

<style scoped>
body,html {
  width: 100%;
  height: 100%;
}
div {
  background-color: cadetblue;
  margin: auto;
  margin-top: 50px;
  width: 800px;
  height: 800px;
  border: solid 3px black;
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
