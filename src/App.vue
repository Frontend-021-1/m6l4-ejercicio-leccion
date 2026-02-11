<script setup>
import { ref } from 'vue'
import SearchForm from './components/SearchForm.vue';
import CardComp from './components/CardComp.vue';
import PanelAccion from './components/PanelAccion.vue';
import ScrollableComp from './components/ScrollableComp.vue';
import BrokenLink from './components/BrokenLink.vue';
import EventLog from './components/EventLog.vue';

const logCaptura = () => {
  console.log('Click capturado: ¿Hiciste click en la Card o en la Section?')
}

const eventLog = ref([])

const createEvent = (type) => {
  console.log('evento', type)
  eventLog.value.push(type)
}

const handleLimpiar = () => {
  console.log('Limpiando...')
  eventLog.value = []
}
</script>

<template>
  <main class="container my-5">
    <h1 class="mb-4">Ejercicio Lección 4 - Manejo de Eventos con Vue</h1>

    <section class="mb-3">
      <h2>1. Formulario de búsqueda</h2>
      <SearchForm @buscar="createEvent" />
    </section>

    <hr class="my-4">

    <section class="mb-3" @click.capture="logCaptura">
      <h2>2. Tarjetas clicables</h2>
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
        <div class="col" v-for="num in 10" :key="num">
          <CardComp :id="num" @click-card="createEvent" @favorito-card="createEvent" />
        </div>
      </div>
    </section>

    <hr class="my-4">

    <section class="mb-3">
      <h2>3. Panel acción única</h2>
      <PanelAccion />
    </section>

    <hr class="my-4">
    <section>
      <h2>4. Elemento Scroll</h2>
      <ScrollableComp @scroll="createEvent" />
    </section>
    <hr class="my-4">
    <section>
      <h2>5. Enlace que no navega</h2>
      <BrokenLink />
    </section>
    <hr class="my-4">
    <section>
      <h2>6. Log de Eventos</h2>
      <EventLog :event-log="eventLog" @limpiar-log="handleLimpiar" />
    </section>
  </main>
</template>

<style scoped></style>
