<template>
  <div id="dns">
    <h1>Inicio dos Estudos - Vue</h1>
    <h2>Meu nome é {{ testando.eu }}, sou do estado da {{ testando.estado }} - {{ testando.pais }}</h2>
    <div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    testando: Object,
  }

}

</script>

<style scoped>
#dns {
  background-color: #dadada;
  max-width: 500;
  height: 350;
  padding: 1%;
  text-align: center;
  margin-top: 2%;
}
</style>
