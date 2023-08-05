<template>
  <div>
    <table>
      <thead>
        <tr>
          <th>id</th>
          <th>Placa</th>
          <th>Modelo</th>
          <th>Marca</th>
          <th>Descripción</th>
          <th>Acciones</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="vehiculo in vehiculos" :key="vehiculo.id">
          <td>{{ vehiculo.id }}</td>
          <td>{{ vehiculo.placa }}</td>
          <td>{{ vehiculo.modelo }}</td>
          <td>{{ vehiculo.marca }}</td>
          <td>{{ vehiculo.descripcion }}</td>
      
        </tr>
                   <button @click="consultarVehiculos()">Visualizar</button>
      </tbody>
    </table>
  </div>
</template>

<script>
import { consultarTodosFachada } from "../helpers/VehiculoCliente";

export default {
  data() {
    return {
      vehiculos: []
    };
  },

  methods: {
    async consultarVehiculos() {
    
        const response = await consultarTodosFachada();
        this.vehiculos = response.data;
        console.log(this.vehiculos);


        if (this.vehiculos.length > 0) {
          const v = this.vehiculos[0];
          this.id = v.id;
          this.placa = v.placa;
          this.modelo = v.modelo;
          this.marca = v.marca;
          this.descripcion = v.descripcion;
        }
     
    },
  },
  mounted() {
    this.consultarVehiculos();
  },
};
</script>


<style>

</style>