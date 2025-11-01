<script setup>
import { ref } from 'vue';

const fechaColor = ref([
  { color: '#D84040' },
  { color: '#8E1616' },
  { color: '#D84040' },
  { color: '#8E1616' },
  { color: '#D84040' }
]);

const educacion = ref([
  {
    fecha: '2024',
    title: 'Técnicatura Universitaria en Programación',
    descripcion:
      'Incumbencias Profesionales: Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos.'
  },
  {
    fecha: '2022',
    title: 'Platzi - Full Stack Web Developer',
    descripcion: 'Escuela de Desarrollo Web'
  },
  {
    fecha: '2022',
    title: 'Soy Henry Bootcamp',
    descripcion: 'Henry Bootcamp. +800 horas de cursado teórico práctico.'
  },
  {
    fecha: '2017',
    title: 'UTN-Mendoza - Tecnicatura en Programación',
    descripcion: 'Título no concluido'
  },
  {
    fecha: '2016',
    title: 'UTN-Mendoza - Ingeniería en Sistemas',
    descripcion: 'Título no concluido'
  }
]);
</script>

<template>
  <ul class="timeline">
    <li
      v-for="(item, index) in educacion"
      :key="index"
      :style="{ '--fecha-color': fechaColor[index].color }"
    >
      <div class="fecha">{{ item.fecha }}</div>
      <h3 class="title">{{ item.title }}</h3>
      <div class="descripcion">{{ item.descripcion }}</div>
    </li>
  </ul>
</template>

<style scoped>
/* ===== BASE ===== */
.timeline {
  --col-gap: 2rem;
  --row-gap: 2.5rem;
  --line-w: 3px;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin: 2rem auto;
  padding: 0;
  position: relative;
}

.timeline::before {
  content: '';
  grid-column: 1;
  grid-row: 1 / span 20;
  background: linear-gradient(180deg, #d84040, #8e1616);
  border-radius: 10px;
}

.timeline li {
  grid-column: 2;
  display: grid;
  grid-template-rows: min-content min-content min-content;
  margin-bottom: var(--row-gap);
}

.timeline li .fecha {
  --dateH: 3.2rem;
  height: var(--dateH);
  text-align: center;
  background: var(--fecha-color);
  color: #eeeeee;
  font-size: 1.1rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
  box-shadow: 0 4px 12px rgba(216, 64, 64, 0.3);
  margin-bottom: 0.8rem;
}

.timeline li .fecha::after {
  content: '';
  position: absolute;
  width: 1rem;
  aspect-ratio: 1;
  background: #1d1616;
  border: 3px solid var(--fecha-color);
  border-radius: 50%;
  top: 50%;
  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
  box-shadow: 0 0 0 4px rgba(216, 64, 64, 0.15);
}

.timeline li .title,
.timeline li .descripcion {
  background: rgba(29, 22, 22, 0.7);
  backdrop-filter: blur(10px);
  position: relative;
  padding: 1rem 1.25rem;
  border: 1px solid rgba(216, 64, 64, 0.3);
  border-radius: 10px;
}

.timeline li .title {
  font-weight: 600;
  color: #eeeeee;
  font-size: 1rem;
}

.timeline li .descripcion {
  margin-top: 0.5rem;
  color: #d1d5db;
  font-size: 0.95rem;
  line-height: 1.4;
}

/* ===== TABLET Y DESKTOP ===== */
@media (min-width: 768px) {
  .timeline {
    grid-template-columns: 1fr var(--line-w) 1fr;
    column-gap: 3rem;
  }

  .timeline::before {
    grid-column: 2;
  }

  .timeline li {
    margin-bottom: var(--row-gap);
  }

  .timeline li:nth-child(odd) {
    grid-column: 1;
  }

  .timeline li:nth-child(even) {
    grid-column: 3;
  }

  .timeline li .fecha {
    font-size: 1.2rem;
  }

  .timeline li:nth-child(odd) .fecha {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }

  .timeline li:nth-child(odd) .fecha::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }
}

/* ===== MOBILE SMALL (extra mejora para <480px) ===== */
@media (max-width: 480px) {
  .timeline {
    --col-gap: 1.5rem;
    --row-gap: 2rem;
    width: 95%;
  }

  .timeline li .fecha {
    font-size: 1rem;
    height: 2.8rem;
  }

  .timeline li .title {
    font-size: 0.95rem;
  }

  .timeline li .descripcion {
    font-size: 0.9rem;
  }
}
</style>
