<template>
  <div id="app">
    <!-- <HelloWorld :testando="meuNome" :showIdade="true"/>
    <HelloWorld :testando="meuNome" :showIdade="false"/>
    <HelloWorld :testando="meuNome" :showIdade="true"/> -->
    

  <div v-for="(cliente, index) in clientes" :key="cliente.id">
    <h4>{{ index + 1 }}</h4>
    <HelloWorld :testando="cliente"/>
    <hr>
  <div>
    <h2>Editar</h2>
    <input type="text" v-model="cliente.nome">
    <input type="text" v-model="cliente.email">
  </div>
  </div>
  </div>
</template>


<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      // meuNome: {
      //   eu: "Aldair Neves da Silva",
      //   estado: "Bahia",
      //   pais: "Brasil",
      //   idade: 23

      // },
      clientes: [
        {
          id: 4,
          nome: "Aldair",
          email: "aldair@gamail.com",
        },
        {
          id: 5,
          nome: "fulano",
          email: "fulano@gamail.com",
        },
        {
          id: 6,
          nome: "Alguem",
          email: "alguem@gamail.com",
        },
        {
          id: 7,
          nome: "Alguem",
          email: "alguem@gamail.com",
        },
        {
          id: 8,
          nome: "Alguem",
          email: "alguem@gamail.com",
        },
      ]

    }
  },
  components: {
    HelloWorld
  }
}
</script>

<style>
/* #app {
  background-color: #2c3e50;
  max-width: 500;
  height: 350;
  padding: 1%;
  text-align: center;
} */
</style>
