<script setup>
import { computed } from 'vue'

const props = defineProps({
  eventLog: {
    type: Array,
    required: true
  }
})

const emit = defineEmits(['limpiarLog'])

const limitedEventLog = computed(() => {
  return props.eventLog.slice(-10)
})
</script>

<template>
  <div>
    <ul>
      <li v-for="event in limitedEventLog">{{ event }}</li>
    </ul>
    <button class="btn btn-warning" @click="emit('limpiarLog')">Limpiar Log</button>
  </div>
</template>

<style scoped>
/* scoped styles here */
</style>