<template>

<div class="formPersonas">


<fieldset>
    <legend>Formulario Registro Persona</legend>
        <form action="">

            <label for="idpersona">id Persona</label><br>
            <input type="text" name="idpersona" id="idpersona" v-model="personaje.idpersona"><br>

            <label for="nombre">nombre</label><br>
            <input type="text" name="nombre" id="nombre" v-model="personaje.nombrePersona"><br>

            <label for="apellidos">apellidos</label><br>
            <input type="text" name="apellidos" id="apellidos" v-model="personaje.apellidoPersona"><br>

            <label for="direccion">direccion</label><br>
            <input type="text" name="direccion" id="direccion" v-model="personaje.direccionPersona"><br>

            <label for="telefono">telefono</label><br>
            <input type="text" name="telefono" id="telefono" v-model="personaje.telefonoPersona"><br><br>

            <button type="submit" v-on:click="guardar()">Guardar</button>
            <button type="submit" v-on:click="eliminar(personaje.idpersona)">Eliminar</button>
        </form>
</fieldset>  

</div>

</template>

<script>
import axios from 'axios'
export default{

name: 'formularioPersonas',
data:function(){
return{
personaje: {
idpersona: "",
nombrePersona: "",
apellidoPersona: "",
direccionPersona: "",
telefonoPersona: ""

}

}
},methods:{

guardar(){

axios.post("http://localhost:8080/api/personaje",this.personaje).then(data=>{

console.log(data)

})
},
eliminar(id){

axios.delete("http://localhost:8080/api/personaje/"+id).then(data=>{

console.log(data)

})

}

}
}
</script>

    
<style scoped>

.formPersonas{

text-align: center;
padding: 5%;
font-family : inherit;

}
</style>