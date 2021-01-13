<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <hr />
   
    <div v-for="(cliente, index) in clientes" :key="cliente.cod">
      <p>{{ index+1 }} </p>
      <Cliente :cliente="cliente" />
      <br>
      <h4>Edição</h4>
      <input type="text" v-model="cliente.nome">
      <br>
      <input type="text" v-model="cliente.email">
      <hr>
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente";

export default {
  name: "App",
  data() {
    return {     
      clientes: [
        {
          cod: 1,
          nome: "Paulo",
          email: "email objeto",
          idade: 20,
        },
        {
          cod: 2,
          nome: "Rodrigo Objeto",
          email: "rodrigo@gmail.com",
          idade: 17,
        },
        {
          cod: 3,
          nome: "Douglas",
          email: "douglas@uol.com.br",
          idade: 44,
        },
        {
          cod: 4,
          nome: "fernando",
          email: "fernando@uol.com.br",
          idade: 38,
        }
      ],
    };
  },
  components: {    
    Cliente,
  },
};
</script>

<style>
</style>
