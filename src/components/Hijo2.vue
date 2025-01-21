<script setup>
import { inject } from 'vue';
const ciclohijo = inject('miCiclo') // Aqui ya tengo acceso a la variable ciclo del padre
const modificar = () => {
    ciclohijo.value = 'DAM'
}
</script>

<template>
    <div>
        <h1>Hijo2:</h1>
        <h2>{{ ciclohijo }}</h2>
        <button @click="modificar">Cambiar</button>
    </div>
</template>