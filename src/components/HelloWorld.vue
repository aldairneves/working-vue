<template>
  <div :class="{ 'dns': !isCliente, 'Cliente': isCliente }">
    <h1>Inicio dos Estudos - Vue</h1>
    <h2>Meu nome é {{ testando.nome }}, sou do estado da {{ testando.email }} - {{ testando.pais }}</h2>
    <p v-if="showIdade === true">Meu nome Verdadeiro é {{ testando.idade }}</p>
    <p v-else>Eu escondir a idade!</p>
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
