<template>
  <div id="app">
    <h3>Cadastro:</h3>
    <input type="texto" placeholder="nome" v-model="nomeField"/><br />
    <input type="texto" placeholder="email"  v-model="emailField"/><br />
    <input type="number" placeholder="idade"  v-model="idadeField"/> <br>
    <button @click="cadastrar">cadastrar</button>
  
    <h1>Guia Clientes</h1>
    <hr />

    <div v-for="(cliente) in clientes" :key="cliente.cod">
      <!--<p>{{ index + 1 }}</p>-->
      <Cliente :cliente="cliente" />
      <!--<br>
      <h4>Edição</h4>
      <input type="text" v-model="cliente.nome">
      <br>
      <input type="text" v-model="cliente.email">
      <hr>-->
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente";

export default {
  name: "App",
  data() {
    return {
      nomeField: "",
      idadeField: "",
      emailField: "",
      clientes: [
        /*{
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
        },*/
      ],
    };
  },
  methods:{
    cadastrar: function(){
      this.clientes.push({
        cod : this.clientes.length+1,
        nome: this.nomeField,
        email: this.emailField,
        idade: this.idadeField,
      });

      this.nomeField  = "";
      this.emailField = "";
      this.idadeField = "";

    }
  },
  components: {
    Cliente,
  },
};
</script>

<style>
</style>
