<script setup>
import { ref } from 'vue'

const busqueda = ref('')

const limpiar = () => {
  busqueda.value = ''
}

const buscar = () => {
  if (busqueda.value === '') {
    console.warn('Por favor, ingrese un término de búsqueda')
    return
  }
  console.log(`Buscando ${busqueda.value}`)
}
</script>

<template>
  <form @submit.prevent="buscar">
    <div class="mb-3">
      <label for="search" class="form-label">Buscar</label>
      <input type="text" name="search" id="search" class="form-control" placeholder="Ej: Auto" v-model.trim="busqueda"
        @keydown.esc="limpiar">
    </div>
    <button type="submit" class="btn btn-primary">Buscar</button>
  </form>
</template>

<style scoped></style>