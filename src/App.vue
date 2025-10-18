<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import EducacionComponente from './components/EducacionComponente.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponente from './components/HabilidadesComponente.vue';
</script>

<template>
  <header>
    <!-- Barra de navegacion -->
    <NavBar />
    <!-- Componente Datos personales -->
    <DatosPersonales />
  </header>
  <main>
    <!-- el estilo css de section se encuentra en base.css -->
    <section id="educacion">
      <h2>Educacion - Cursos</h2>
      <!-- Componente educacion -->
      <EducacionComponente />
    </section>
    <section id="experiencia">
      <h2>Experiencia</h2>
      <!-- Componente experiencia -->
      <ExperienciaComponente />
    </section>
    <section id="proyectos">
      <h2>Proyectos</h2>
      <!-- Componente proyectos -->
      <ProyectosComponente/>
    </section>
    <section id="habilidades">
      <h2>Habilidades</h2>
      <!-- Componente habilidades -->
      <HabilidadesComponente/>
    </section>
    <section id="intereses"><h2>Intereses</h2></section>
  </main>
</template>

<style scoped>

</style>
