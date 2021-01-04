<template>
  <v-container>
    <v-toolbar>
     

      <v-toolbar-title>Soluciones MisionTIC</v-toolbar-title>
      <v-spacer></v-spacer>
      
      <v-btn
      icon
      class="mr-5"
      to="/login"
      >
        <v-icon>mdi-logout</v-icon>
        <span>Login</span>
      </v-btn>
    </v-toolbar>
    
    <carausel></carausel>
    <br>
    <h1  class="font-weight-bold">QUIENES SOMOS?</h1 >
    <p class="font-weight-bold text-justify">
      Somos una institución de Desarrollo, regulada y confiable que brinda soluciones de crecimiento empresarial.
      Conocemos los retos a los que se enfrentan las pequeñas, medianas y grandes empresas, por lo cual otorgamos soluciones de optimización empresariales de forma rápida y con atención 100% personalizada.
      Nos diferenciamos por la velocidad en la que ponemos a su disposición los recursos y herramientas que necesita para impulsar su negocio.

    </p>
    <section-api></section-api>
    <nuestro-footer></nuestro-footer>
    
  </v-container>
  
</template>

<script>
import Carausel from './Carausel.vue'
import SectionApi from './SectionApi.vue'
import NuestroFooter from './NuestroFooter.vue'

  export default {
  components: { Carausel , SectionApi, NuestroFooter},
    name: 'HelloWorld',  
   

   
    
  }
</script>
<style >
h1 {
    text-align:center;
    color:cornflowerblue
}

</style>
