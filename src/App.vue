<template>
  <div id="app">
    <!-- <HelloWorld :testando="meuNome" :showIdade="true"/>
    <HelloWorld :testando="meuNome" :showIdade="false"/>
    <HelloWorld :testando="meuNome" :showIdade="true"/> -->
    <h1>Cadastro: </h1>
    <small id="nomeerro" v-show="deuErro">Nome invalido. Tente Novamente</small> <br>
    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="email" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="numero" v-model="numeroField"> <br>
    <button @click="cadastra()">Cadastrar</button>

    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h4>{{ index + 1 }}</h4>
      <HelloWorld :testando="cliente" @delete="deletarUsuario($event)" />
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
      deuErro: false,
      nomeField: "",
      emailField: "",
      numeroField: "",
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
  },
  methods: {
    cadastra: function () {
      if (this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 2) {
        this.deuErro = true;
        console.log("erro de validação")
      } else {
        this.clientes.push({ nome: this.nomeField, email: this.emailField, numero: this.numeroField, id: Date });
        this.nomeField = "";
        this.emailField = "";
        this.numeroField = "";
        this.deuErro = false;
      }

    },
    deletarUsuario: function ($event) {
      console.log("Evento Recebido");
      console.log($event.idDoCliente);
      var id = $event.idDoCliente;
      var novoArray = this.clientes.filter(cliente => cliente.id != id);
      this.clientes = novoArray;
      console.log("deletado")

    }
  }
}
</script>

<style>
#app {
  background-color: #2c3e50;
  max-width: 500;
  height: 350;
  padding: 1%;
  text-align: center;
}

#nomeerro {
  color: red;
}
</style>
