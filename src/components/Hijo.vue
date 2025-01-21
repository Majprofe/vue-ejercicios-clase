<script setup>
const props = defineProps({
    nombre: String,
    edad: Number
})

const emit = defineEmits(['modificar'])
const enviar = () => {
    emit ('modificar', 'Vue', 9)
}
</script>

<template>
<div>
    <h1>Hijo:</h1>
    <h2>Te llamas {{ nombre }}  y tienes {{ edad }} años</h2>
    <button @click="enviar">Cambiar valores</button>
</div>
</template>