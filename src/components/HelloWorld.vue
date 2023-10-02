<template>
  <div :class="{ 'dns': !isCliente, 'Cliente': isCliente }">
    <h1>Inicio dos Estudos - Vue</h1>
    <h2>Meu nome é {{ testando.nome }}, sou do estado da {{ testando.email }} - {{ testando.pais }}</h2>
    <p v-if="showIdade === true">Meu nome Verdadeiro é {{ testando.idade }}</p>
    <p v-else>Eu escondir a idade!</p>
    <button @click="mudarCor()">mudar a cor</button>
    <button @click="eventoDeletar()">Deletar</button>
    <hr>
    <div>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      isCliente: true
    }
  },
  props: {
    testando: Object,
    showIdade: Boolean
  },
  methods: {
    mudarCor: function () {
      this.isCliente = !this.isCliente;
    },
    eventoDeletar: function () {
      console.log("Componente Filho")
      this.$emit("delete", { idDoCliente: this.testando.id, cidade: "Itaquara", components: this })
    }
  }

}

</script>

<style scoped>
.dns {
  background-color: #dadada;
  max-width: 500;
  height: 350;
  padding: 1%;
  text-align: center;
  margin-top: 2%;
}

.Cliente {
  background-color: #338bff;
  max-width: 500;
  height: 350;
  padding: 1%;
  text-align: center;
  margin-top: 2%;
  color: #fff;
}
</style>
