<script setup>
import codeIcon from '/src/assets/code.svg';
import efficiencyIcon from '/src/assets/efficiency.svg';
import networkIcon from '/src/assets/network.svg';
import designIcon from '/src/assets/design.svg';
import rocketIcon from '/src/assets/rocket.svg';
import { ref } from 'vue';

const titulo = 'Ingeniero de Software en Nación Servicios';
const fecha = 'Desde Agosto 2023 / Actualidad';
const experiencias = ref([
  { id: 1, src: codeIcon, parrafo: 'Desarrollo y mantenimiento full stack de aplicaciones web corporativas utilizando tecnologías como Node.js, Express, Vue y PostgreSQL.' },
  { id: 2, src: efficiencyIcon, parrafo: 'Optimización del rendimiento y refactorización de código existente para mejorar la escalabilidad y mantenibilidad del sistema.' },
  { id: 3, src: networkIcon, parrafo: 'Implementación de integraciones con APIs internas y externas, garantizando la seguridad y consistencia de los datos.' },
  { id: 4, src: designIcon, parrafo: 'Colaboración con equipos de diseño y QA para asegurar una experiencia de usuario fluida y de alta calidad.' },
  { id: 5, src: rocketIcon, parrafo: 'Automatización de despliegues y monitoreo de servicios mediante herramientas de CI/CD y contenedores Docker.' }
]);
</script>

<template>
  <div class="experience-card">
    <div class="experience-header">
      <h3 class="titulo">{{ titulo }}</h3>
      <p class="fecha">{{ fecha }}</p>
    </div>

    <ul class="listado">
      <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
        <img class="imagen-svg" :src="experiencia.src" :alt="experiencia.parrafo" />
        <p>{{ experiencia.parrafo }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.experience-card {
  max-width: 900px;
  margin: 3rem auto;
  padding: 2.5rem;
  background: rgba(29, 22, 22, 0.7);
  backdrop-filter: blur(10px);
  border: 2px solid rgba(216, 64, 64, 0.3);
  border-radius: 15px;
  box-shadow: 0 8px 32px rgba(216, 64, 64, 0.15);
  transition: all 0.3s ease;
}

.experience-card:hover {
  background: rgba(29, 22, 22, 0.9);
  border-color: rgba(216, 64, 64, 0.6);
  box-shadow: 0 12px 40px rgba(216, 64, 64, 0.25);
}

.experience-header {
  margin-bottom: 2rem;
  border-bottom: 2px solid rgba(216, 64, 64, 0.4);
  padding-bottom: 1.5rem;
}

.titulo {
  font-size: 1.4rem;
  color: #d84040;
  margin-bottom: 0.5rem;
  font-weight: 700;
}

.fecha {
  font-size: 0.95rem;
  color: #eeeeee;
  margin: 0;
}

.listado {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  list-style: none;
  padding: 0;
  margin: 0;
}

.item {
  display: flex;
  align-items: flex-start;
  gap: 1.5rem;
  padding: 1.5rem;
  background: rgba(216, 64, 64, 0.08);
  border: 1px solid rgba(216, 64, 64, 0.25);
  border-radius: 10px;
  transition: all 0.3s ease;
}

.item:hover {
  background: rgba(216, 64, 64, 0.15);
  border-color: rgba(216, 64, 64, 0.5);
  transform: translateX(5px);
}

.imagen-svg {
  width: 50px;
  height: 50px;
  flex-shrink: 0;
  filter: brightness(0) invert(1);
  opacity: 0.8;
  transition: opacity 0.3s ease, filter 0.3s ease;
}

.item:hover .imagen-svg {
  opacity: 1;
  filter: brightness(0) invert(1) drop-shadow(0 0 6px #d84040);
}

p {
  color: #eeeeee;
  line-height: 1.6;
  margin: 0;
  font-size: 0.95rem;
}

/* Tablet */
@media (max-width: 768px) {
  .experience-card {
    padding: 1.8rem;
    margin: 2rem 1rem;
  }

  .titulo {
    font-size: 1.2rem;
    text-align: center;
  }

  .fecha {
    text-align: center;
    font-size: 0.9rem;
  }

  .item {
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 1.2rem;
    gap: 1rem;
  }

  .imagen-svg {
    width: 45px;
    height: 45px;
  }

  p {
    font-size: 0.9rem;
  }
}

/* Mobile pequeño */
@media (max-width: 480px) {
  .experience-card {
    padding: 1.2rem;
    border-width: 1px;
  }

  .titulo {
    font-size: 1.05rem;
  }

  .fecha {
    font-size: 0.85rem;
  }

  .item {
    padding: 1rem;
    gap: 0.8rem;
  }

  .imagen-svg {
    width: 38px;
    height: 38px;
  }

  p {
    font-size: 0.88rem;
    line-height: 1.5;
  }
}
</style>
