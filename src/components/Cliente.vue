<template>
    <!--
        1 way -> atualiza em tempo real apenas a leitura
        2 way -> atualiza em tempo real a escrita e a leitura
    -->
    <div :class="{'cliente':!IsPremium,'cliente-premium':IsPremium}">
        <h2>{{cliente.cod +' - '+cliente.nome}}</h2>
        <hr>
        <p> E-mail: {{ cliente.email }}</p>
        <p v-if="OPIdade"> Idade: {{ cliente.idade }} </p>
        <p v-else>Sem idade </p>
        <button @click="mudarClasse">Mudar classe</button>
        <button @click="emitirEventoDelete"> Excluir </button>
        <h4>id especial {{ codEspecial }} </h4>



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
  data() {
    return {
      IsPremium: false,
    };
  },
  props: {
    cliente: Object,
    OPIdade: Boolean,
  },
  methods: {
    mudarClasse: function () {
      this.IsPremium = !this.IsPremium;
    },
    emitirEventoDelete: function () {
      this.$emit("meDelete", {
        cod: this.cliente.cod,
        curso: "aqui vai o teste",
        emPromocao: true,
        component: this,
      });
    },
    testar: function () {
      console.log("Testando");
    },
  },
  computed: {
    codEspecial: function () {
      return (
        this.cliente.email +
        this.cliente.nome +
        this.cliente.cod
      ).toUpperCase();
    },
  },
};
</script>

<style scoped>
/*Scoped siginifica que o style so se referenciara com este .vue*/
.cliente {
  background-color: #ece5e3;
  max-width: 600px;
  height: 100%;
  padding: 10px;
  margin-top: 8px;
}
.cliente-premium {
  background-color: black;
  color: rgb(248, 166, 59);
  max-width: 600px;
  height: 100%;
  padding: 10px;
  margin-top: 8px;
}
</style>