# l4-ejercicio-leccion

## Ejercicio Manejo de Eventos en Vue

Desarrolla una mini-app “Centro de Eventos” con estos módulos:

### 1. Formulario de búsqueda

- [x] Campo input con:
  - [x] `@keyup.enter="buscar"` para ejecutar búsqueda
  - [x] `@keydown.esc="limpiar"` para limpiar el campo
- [x] Botón Buscar dentro de un `<form>` con `@submit.prevent="buscar"` (evita recarga)
- [x] Muestra resultado o mensaje si está vacío

### 2. Tarjetas clicables (bubbling y propagación)

- [x] Un contenedor <section> con varias tarjetas.
- [x] Cada tarjeta tiene un `@click="seleccionarTarjeta(id)"`.
- [x] Dentro de la tarjeta, un botón “Favorito” con `@click.stop="marcarFavorito(id)"` para evitar que el click “burbujee” hacia la tarjeta.
- [x] Agrega en el contenedor un `@click.capture="logCaptura"` para evidenciar el orden de captura vs burbujeo (muestra en el registro el orden de disparo).

### 3. Panel “acción única”

- [x] Un botón “Mostrar tips” con @click.once="mostrarTips" que solo funcione una vez.
- [x] Después de ejecutarse, deshabilita o cambia el texto del botón.

### 4. Caja scrollable con rendimiento

- [x] Un contenedor con overflow: auto; height: 200px y varios elementos para forzar scroll.
- [x] Maneja el evento de scroll con @scroll.passive="onScroll" y refleja la posición en un indicador. (Tip: con .passive no llames event.preventDefault().)

### 5. Enlace que no navega

- [x] Un <a href="https://example.com"> que no debe navegar: `@click.prevent="abrirModalInfo"`.

### 6. Registro de eventos (audit log)

- [ ] Un panel donde se listen en tiempo real los últimos N eventos (p. ej., ['buscar', 'limpiar', 'click tarjeta 3', 'favorito 2', 'scroll: 145px', ...]).
- [ ] Botón para limpiar el registro

## Project Setup

```sh
pnpm install
```

### Compile and Hot-Reload for Development

```sh
pnpm dev
```

### Compile and Minify for Production

```sh
pnpm build
```
