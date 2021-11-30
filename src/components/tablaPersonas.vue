<template>
    <div class="tablaPersonas">
  

        <fieldset>
            <legend>Tabla de Dueños</legend>
<table>
  <tr>
    <th>id</th>
    <th>nombre</th>
    <th>apellidos</th>
    <th>direccion</th>
    <th>telefono</th>
  </tr>
  <tr v-for="personaje in personajes" :key="personaje.idpersona">
    <td>{{personaje.idpersona}}</td>
    <td>{{personaje.nombrePersona}}</td>
    <td>{{personaje.apellidoPersona}}</td>
    <td>{{personaje.direccionPersona}}</td>
    <td>{{personaje.telefonoPersona}}</td>
  </tr>
  
</table>
        </fieldset>

        <router-view/>
    </div>

</template>

<script>

import axios from 'axios'
export default{

name: 'tablaPersonas',
data(){
    return{
        personajes:[]
    }
},mounted(){
    let vue=this;
    axios.get("http://localhost:8080/api/personaje/listar").then(response =>{
        vue.personajes=response.data;
    })
}

}

</script>

<style scoped>

.tablaPersonas{
padding: 5%;
text-align: center;

}
table{
    
    border: 1px solid #000;
    margin: auto;
    padding: 1 px;
}
th{

border: 1px solid #000;

}
tr,td{
    
    width: 20%;
   text-align: left;
   vertical-align:top;
   border: 1px solid #000;
}
</style>