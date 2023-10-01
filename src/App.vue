<template>
  <div>
    <HelloWorld :testando="meuNome" />
  </div>
</template>


<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() {
    return {
      meuNome: {
        eu: "Aldair Neves da Silva",
        estado: "Bahia",
        pais: "Brasil"

      }

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
