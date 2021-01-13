<template>
    <!--
        1 way -> atualiza em tempo real apenas a leitura
        2 way -> atualiza em tempo real a escrita e a leitura
    -->
    <div id="cliente">
        <h2>{{nome}}</h2>
        <hr>
        <p> E-mail: {{ email }}</p>
        <p> Idade: {{ idade }} </p>



        <!-- CASO QUEIRA VER COMO FUNCIONA OS DATA BINDING, DESCOMENTAR LINHA ABAIXO -->
        <!--<h3>Descrição do cliente: {{ descricao }}</h3>
        <p>1 Way </p>
        <input type="text" :value="nome">--> <!-- 1 way data biding -->
        <!--
        <hr>
        <p> 2 way </p>
        <input type="text" v-model="nome"> --><!-- 2 way data biding -->
    </div>  
</template>

<script>
export default {
    data(){
        return {
            
        }
    },
    props:{
        nome:String,
        idade:Number,
        descricao:String,
        email:String,
        numero:Number,
    }
}
</script>

<style scoped> /*Scoped siginifica que o style so se referenciara com este .vue*/
  #cliente{
      background-color: #ECE5E3;
      max-width: 600px;
      height: 100%;
      padding: 10px;
      margin-top:8px;
  }

</style>