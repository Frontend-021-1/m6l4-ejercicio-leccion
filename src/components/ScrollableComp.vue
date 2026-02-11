<script setup>

const emit = defineEmits(['scroll'])

const onScroll = (event) => {
  // console.log(event)
  console.log(`'Scroll: ${event.target.scrollTop}px`) // distancia del scroll desde parte superior del elemento
  emit('scroll', `Scroll: ${event.target.scrollTop}px`)
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