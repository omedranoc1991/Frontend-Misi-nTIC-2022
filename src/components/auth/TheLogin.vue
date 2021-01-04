<template>


 <v-app>
    <v-card width="400px" class="mx-auto my-12">
      <v-card-title class="pb-0">
        <h2>Login</h2>
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field 
             v-model="login.email"    
             label="E-mail"
             required
             prepend-icon="mdi-account-circle"
          />
          <v-text-field 
            v-model="login.password"  
            label="Contraseña"
            type="password"
            required
            prepend-icon="mdi-lock"
          />
        </v-form>
      </v-card-text>
      <v-card-actions>
        
        <v-btn
         :disabled="!(this.login.password && this.login.email)"
         color="success"
         class="mr-4"
         block
         @click="loginUser"
        >Login</v-btn>
      </v-card-actions>
    </v-card>
  </v-app>
    

  
</template>

<script>
import swal from 'sweetalert';
import axios from 'axios'
export default {
    name: 'TheLogin',
    data(){
        return{
            login:{
                email : '',
                password: ''
            }
        }
    },
    beforeCreate(){
        this.$store.dispatch('autoLogin')
    },
    methods:{
        
        loginUser(){
            axios.post('http://localhost:3000/api/usuario/login', this.login)
        .then(response =>{
            return response.data
        })
        .then(data =>{ 
            this.$store.dispatch('guardarToken', data.tokenReturn)
            this.$router.push({name: "Segura"})
            swal("Bienvenido", "Datos de inicio de sesion correctos", "success");            
        })
        .catch(error =>{
            console.log(error)
            swal("Error", "Datos de inicio de sesion no coinciden o no se encuentran", "error")
            return error
        })
           
        }
    }
}
</script>