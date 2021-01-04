<template>

<div >
    <v-card
    
    class="mx-auto my-12"
    max-width="374"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="250"
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
    ></v-img>

    <v-card-title v-for="dato of datos" :key="dato.id">{{dato.titulo}}</v-card-title>
      <div></div>
    

    <v-divider class="mx-4"></v-divider> 

    
  </v-card>
</div>
  

    
</template>

<script>
export default {
    name: "Servicios",
    data(){
        return{
            datos: [{
                id: null,
                titulo:"",
                contenido:""
            }],
            
        }
        console.log(datos)
    },
    mounted() {
    this.list()
  },
    methods:{
          list(){
      axios.get('http://localhost:3000/api/articulo/list')
      .then(response=>{
          this.datos.id= response.data.id
          this.datos.titulo = response.data.nombre
          this.datos.contenido = response.data.descripcion
          console.log(response)
      })
      .catch(error=>{
        console.log(error)
      })
    }, 
    
    }
}
</script>