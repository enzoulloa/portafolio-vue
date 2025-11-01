<script setup>
import NavBar from './components/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import EducacionComponente from './components/EducacionComponente.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponente from './components/HabilidadesComponente.vue';
import InteresesComponente from './components/InteresesComponente.vue';
import MeshBackground from './components/MeshBackground.vue';
import AnimatedDotsBackground from './components/AnimatedDotsBackground.vue';
import { ref } from 'vue';

const animationChoice = ref(2);
</script>

<template>
  <NavBar />

  <header>
    <DatosPersonales />
  </header>

  <main>
    <section id="educacion" class="section">
      <h2>Educación & Cursos</h2>
      <EducacionComponente />
    </section>

    <section id="experiencia" class="section">
      <h2>Experiencia</h2>
      <ExperienciaComponente />
    </section>

    <section id="proyectos" class="section">
      <h2>Proyectos</h2>
      <ProyectosComponente />
    </section>

    <section id="habilidades" class="section">
      <h2>Habilidades</h2>
      <HabilidadesComponente />
    </section>

    <section id="intereses" class="section section-animated">
      <MeshBackground v-if="animationChoice === 1" />
      <AnimatedDotsBackground v-if="animationChoice === 2" />

      <div class="section-content">
        <h2>Intereses</h2>
        <InteresesComponente />
      </div>
    </section>
  </main>

  <footer>
    <a href="#top">↑ Volver al inicio</a>
    <p>© 2025 Enzo Ulloa - Portafolio Web</p>
  </footer>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  background-color: #1D1616;
  color: #EEEEEE;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>

<style scoped>
/* ------------------ Secciones ------------------ */
.section {
  padding: 4rem 2rem;
  border-top: 2px solid #D84040;
  transition: all 0.3s ease;
  background: rgba(29, 22, 22, 0.85);
  backdrop-filter: blur(8px);
  border-radius: 12px;
  max-width: 1200px;
  margin: 2rem auto;
}

.section h2 {
  text-align: center;
  font-size: 2.5rem;
  color: #EEEEEE;
  margin-bottom: 3rem;
  font-weight: 700;
  letter-spacing: 1px;
  position: relative;
}

.section h2::after {
  content: '';
  display: block;
  width: 60px;
  height: 3px;
  background: #D84040;
  margin: 1rem auto 0;
  border-radius: 2px;
}

/* ------------------ Sección animada ------------------ */
.section-animated {
  position: relative;
  overflow: hidden;
}

.section-animated .section-content {
  position: relative;
  z-index: 1;
}

/* Fondo animado suavizado */
.section-animated::before {
  content: '';
  position: absolute;
  inset: 0;
  background: inherit;
  opacity: 0.15;
  filter: blur(5px);
  z-index: 0;
}

/* ------------------ Footer ------------------ */
footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: #1D1616;
  padding: 3rem 2rem;
  border-top: 2px solid #D84040;
  text-align: center;
  gap: 1rem;
}

footer a {
  color: #D84040;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  font-size: 1.1rem;
}

footer a:hover {
  color: #EEEEEE;
  text-decoration: underline;
  text-shadow: 0 0 10px #D84040;
}

footer p {
  color: #EEEEEE;
  margin: 0;
  font-size: 0.9rem;
}

/* ------------------ Responsive ------------------ */
@media (max-width: 1024px) {
  .section {
    padding: 3rem 1.5rem;
  }

  .section h2 {
    font-size: 2.2rem;
  }
}

@media (max-width: 768px) {
  .section {
    padding: 2rem 1rem;
    margin: 1.5rem auto;
  }

  .section h2 {
    font-size: 1.8rem;
    margin-bottom: 2rem;
  }

  footer {
    padding: 2rem 1rem;
    gap: 0.5rem;
  }

  footer a {
    font-size: 1rem;
  }

  footer p {
    font-size: 0.85rem;
  }
}
</style>
