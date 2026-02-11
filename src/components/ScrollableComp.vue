<script setup>

const onScroll = (event) => {
  // console.log(event)
  console.log(`'Scroll: ${event.target.scrollTop}px`) // distancia del scroll desde parte superior del elemento
}
</script>

<template>
  <div class="scrollable" @scroll.passive="onScroll">
    <p v-for="num in 100" :key="num">Párrafo {{ num }}</p>
  </div>
</template>

<style scoped>
.scrollable {
  height: 200px;
  overflow: auto;
}
</style>