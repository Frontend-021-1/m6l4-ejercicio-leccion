<script setup>
import { ref, computed } from 'vue'

const disabled = ref(false)

const mostrarTips = () => {
  console.log('Acción única del botón')
  disabled.value = true
}

const textoBoton = computed(() => {
  return disabled.value ? 'Botón deshabilitado' : 'Mostrar Tips'
})
</script>

<template>
  <!-- Si el atributo y la variable se llaman igual (como ahora con disabled), podemos escribir :disabled que sería lo mismo que :disabled="disabled" -->
  <button class="btn btn-success" @click.once="mostrarTips" :disabled>{{ textoBoton }}</button>
</template>

<style scoped></style>