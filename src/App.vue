<template>

  <DatosVehiculos/>
</template>

<script>

import DatosVehiculos from "./modules/vehiculo/Components/DatosVehiculos.vue"

export default {
  name: 'App',
  components: {

    DatosVehiculos
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
