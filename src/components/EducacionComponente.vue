<script setup>
import { ref } from 'vue';
const fechaColor = ref([]);
fechaColor.value = [
  {color: '#D84040'},
  {color: '#8E1616'},
  {color: '#D84040'},
  {color: '#8E1616'},
  {color: '#D84040'}
];

const educacion = ref([
  {fecha: '2024', title: 'Técnicatura Universitaria en Programación', descripcion: 'Incumbencias Profesionales: Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos.'},
  {fecha: '2022', title: 'Platzi - Full Stack Web Developer', descripcion: 'Escuela de Desarrollo Web'},
  {fecha: '2022', title: 'Soy Henry Bootcamp', descripcion: 'Henry Bootcamp. +800 horas de cursado teórico práctico.'},
  {fecha: '2017', title: 'UTN-Mendoza - Tecnicatura en Programación', descripcion: 'Titulo no concluido'},
  {fecha: '2016', title: 'UTN-Mendoza - Ingeniería en Sistemas', descripcion: 'Titulo no concluido'}
]);
</script>

<template>
    <ul class="timeline">
        <li v-for="(item, index) in educacion" :key="index" :style="{ '--fecha-color': fechaColor[index].color}">
        <div class="fecha">{{ item.fecha }}</div>
        <h3 class="title">{{ item.title }}</h3>
        <div class="descripcion">{{ item.descripcion }}</div>
    </li>
    </ul>
</template>

<style scoped>
ul {
    --col-gap: 2rem;
    --row-gap: 2.5rem;
    --line-w: 3px;
    display: grid;
    grid-template-columns: var(--line-w) 1fr;
    grid-auto-columns: max-content;
    column-gap: var(--col-gap);
    list-style: none;
    width: min(60rem, 90%);
    margin: 2rem auto;
    padding: 0;
}

ul::before {
    content: "";
    grid-column: 1;
    grid-row: 1 / span 20;
    background: linear-gradient(180deg, #D84040, #8E1616);
    border-radius: 10px;
}

ul li:not(:last-child) {
    margin-bottom: var(--row-gap);
}

ul li {
    grid-column: 2;
    --inlineP: 1.5rem;
    margin-inline: var(--inlineP);
    grid-row: span 2;
    display: grid;
    grid-template-rows: min-content min-content min-content;
}

ul li .fecha {
    --dateH: 3.5rem;
    height: var(--dateH);
    margin-inline: calc(var(--inlineP) * -1);
    text-align: center;
    background: var(--fecha-color);
    color: #EEEEEE;
    font-size: 1.25rem;
    font-weight: 700;
    display: grid;
    place-content: center;
    position: relative;
    border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
    box-shadow: 0 4px 15px rgba(216, 64, 64, 0.4);
}

ul li .fecha::before {
    content: "";
    width: var(--inlineP);
    aspect-ratio: 1;
    background: var(--fecha-color);
    position: absolute;
    top: 100%;
    clip-path: polygon(0 0, 100% 0, 0 100%);
    right: 0;
}

ul li .fecha::after {
    content: "";
    position: absolute;
    width: 1.2rem;
    aspect-ratio: 1;
    background: #1D1616;
    border: 3px solid var(--fecha-color);
    border-radius: 50%;
    top: 50%;
    transform: translate(50%, -50%);
    right: calc(100% + var(--col-gap) + var(--line-w) / 2);
    box-shadow: 0 0 0 4px rgba(216, 64, 64, 0.2);
}

ul li .title,
ul li .descripcion {
    background: rgba(29, 22, 22, 0.6);
    backdrop-filter: blur(10px);
    position: relative;
    padding-inline: 1.5rem;
    border: 1px solid rgba(216, 64, 64, 0.3);
    border-radius: 10px;
}

ul li .title {
    padding-block: 1.5rem 1rem;
    font-weight: 600;
    color: #EEEEEE;
    font-size: 1.1rem;
}

ul li .descripcion {
    padding-block: 1rem 1.5rem;
    font-weight: 400;
    color: #D1D5DB;
    font-size: 0.95rem;
}

@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul::before {
    grid-column: 2;
  }
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  ul li:nth-child(even) {
    grid-column: 3;
  }

  ul li:nth-child(2) {
    grid-row: 2/4;
  }

  ul li:nth-child(odd) .fecha::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
  }

  ul li:nth-child(odd) .fecha::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }

  ul li:nth-child(odd) .fecha {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }
}
</style>
