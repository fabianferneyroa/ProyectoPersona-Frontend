<template>
<div class="pers">
<formularioPersona/>
<tablaPersonas/>
</div>
</template>
<script>
import formularioPersona from '@/components/formularioPersona.vue'
import tablaPersonas from '@/components/tablaPersonas.vue'

export default {
   name: '',
   components: {

formularioPersona,
tablaPersonas

   }
}
</script>
<style scoped>
.pers{
    text-align: center;
}
</style>
