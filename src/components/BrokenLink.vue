<script setup>

const abrirModalInfo = () => {
  console.log('Abriendo modal...')
}
</script>

<template>
  <!-- content here -->
  <a href="https://www.google.com" @click.prevent="abrirModalInfo">Ir a Google</a>
</template>

<style scoped>
/* scoped styles here */
</style>