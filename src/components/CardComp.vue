<script setup>
const props = defineProps({
  id: {
    type: Number,
    required: true
  }
})

const seleccionarTarjeta = () => {
  console.log(`Tarjeta seleccionada: ${props.id}`)
}

const marcarFavorito = () => {
  console.log(`Tarjeta marcada como favorita ${props.id}`)
}
</script>

<template>
  <div class="card" @click.stop="seleccionarTarjeta">
    <div class="card-body">
      <h5 class="card-title">Tarjeta {{ props.id }}</h5>
      <button class="btn btn-primary" @click="marcarFavorito">Favorito</button>
    </div>
  </div>
</template>

<style scoped>
/* scoped styles here */
</style>