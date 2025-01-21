<script setup>
import {ref, provide} from 'vue'
import Hijo from './Hijo.vue'
import Hijo2 from './Hijo2.vue'

const ciclo = ref('DAW')
provide('miCiclo', ciclo)

const nombre = ref('Manuel')
const edad = ref(18)

const cambiarValor = (valor1, valor2)=>{
    nombre.value = valor1
    edad.value = valor2
}
</script>

<template>
  <div>
    <h1>Padre:</h1>
    <Hijo :nombre="nombre" :edad="edad" @modificar="cambiarValor"/>
    <Hijo2 />
  </div>
</template>