<script setup>
import { ref, computed } from 'vue'
import Padre from './components/Padre.vue'
const miNombre = 'Manuel'
const miEdad = 18
const miColor = ref('azul')
const selector = 'azul'
const saludar = (nombre) => {
  console.log(`Hola ${nombre}`)
}
const contador = ref(0)
const incrementar = () => {
  contador.value++
  if (contador.value > 5) {
    miColor.value = 'verde'
  }
  if (contador.value >= 0 && contador.value < 5) {
    miColor.value = 'azul'
  }
  visible.value = contador.value === 0
}
const decrementar = () => {
  contador.value--
  if (contador.value < 0) {
    miColor.value = 'rojo'
  }
  visible.value = contador.value === 0
}

const tareas = ref(['Comprar pan', 'Hacer la comida', 'Estudiar'])

const visible = ref(true)

const comprobacion = computed (() => {
  return contador.value === 0
})
</script>
<template>
  <h1 :class="selector">
    Hola soy {{ miNombre }} y tengo {{ miEdad }}
  </h1>
  <button @click="saludar(miNombre)">Aceptar</button>
  <br />
  <button @click="incrementar">+</button>
  <span :class="miColor">{{ contador }}</span>
  <button @click="decrementar">-</button>
  <br />
  <div v-if="contador < 0">Escribe una cantidad mayor de 0</div>
  <div v-else-if="contador >= 5">Escribe una cantidad menor de 5</div>
  <div v-else>La cantidad es correcta</div>
  <div v-show="comprobacion">No está permitido el número 0</div>
  <ul>
    <li v-for="(tarea, index) in tareas" :key="index">{{ tarea }}</li>
  </ul>
  <Padre />
</template>

<style scoped>
span {
  padding: 0 5px;
}

.rojo {
  color: red;
}

.verde {
  color: green;
}

.azul {
  color: blue;
}
</style>
