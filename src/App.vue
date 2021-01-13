<template>
  <div id="app">
      <h1>Guia Clientes</h1>
      <hr>
      <p> Altere o texto do input para alterar o primeiro cliente:
      <input type="text" v-model="nome1">
      <hr>
      <Cliente :nome="nome1" idade="20" email="paulo@gmail.com"/>      
      <Cliente nome="Rodrigão" idade="40" email="progr" />      
      

  </div>
</template>

<script>
import Cliente from './components/Cliente';

export default {
  name: 'App',
  data(){
    return {
      nome1:"Paulo1",
    }
  },
  components: {
    Cliente
  }
}
</script>

<style>
</style>
