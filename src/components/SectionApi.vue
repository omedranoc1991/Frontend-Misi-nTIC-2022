<template>
  <div id="servicios" class="row">
    <div
      class="card col-md-6"
      v-for="(servicio, index) of servicio"
      :key="index"
    >
      <div class="d-flex justify-content-center p-2">
        <img src="https://picsum.photos/200" alt="Movie Poster" />
      </div>

      <div class="card-body">
        <h5 class="card-title text-center">{{ servicio.nombre }}</h5>
        <p class="card-text text-center">
             {{ servicio.descripcion }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "SectionApi",
  data() {
    return {
      servicio: null,
    };
  },
  mounted() {
    axios
      .get(`http://localhost:3000/api/articulo/list`)
      .then((response) => {
        this.servicio = response.data;
        console.log(this.servicio);
      });
  },
};
</script>