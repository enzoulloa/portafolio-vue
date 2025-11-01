<script setup>
import { ref } from 'vue';

const intereses = ref([
    '💻 Tecnología: Me apasiona mantenerme al día con las últimas innovaciones, aprender nuevos lenguajes y explorar tendencias como la inteligencia artificial y el desarrollo web moderno.',
    '⚽ Fútbol: Disfruto mirar y jugar al fútbol, siguiendo las principales ligas y torneos, y compartiendo la pasión por este deporte con amigos.',
    '🎮 E-sports: Me interesa el mundo competitivo de los videojuegos, especialmente títulos como Counter Strike y otros juegos de estrategia en equipo.',
    '✈️ Viajes: Me gusta conocer nuevos lugares, culturas y comidas, aprovechando cada viaje como una oportunidad de aprendizaje y desconexión.'
]);
</script>

<template>
  <div class="intereses-contenedor">
    <ul class="contenedor-lista">
      <li class="item" v-for="(interes, index) in intereses" :key="index">
        {{ interes }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
.intereses-contenedor {
  max-width: 900px;
  margin: 0 auto;
  padding: 2.5rem 2rem;
}

.contenedor-lista {
  list-style: none;
  padding: 0;
  margin: 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.75rem;
}

.item {
  background: rgba(216, 64, 64, 0.45);
  border: 1px solid rgba(216, 64, 64, 0.25);
  padding: 1.5rem;
  border-radius: 14px;
  color: #EEEEEE;
  font-size: 0.95rem;
  line-height: 1.6;
  transition: all 0.3s ease;
}

.item:hover {
  background: rgba(216, 64, 64, 0.2);
  border-color: rgba(216, 64, 64, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 6px 18px rgba(216, 64, 64, 0.2);
}

/* Tablets */
@media (max-width: 768px) {
  .intereses-contenedor {
    padding: 1.8rem 1.5rem;
  }

  .contenedor-lista {
    grid-template-columns: 1fr;
    gap: 1.25rem;
  }

  .item {
    padding: 1.2rem;
    font-size: 0.9rem;
  }
}

/* Móviles pequeños */
@media (max-width: 480px) {
  .intereses-contenedor {
    padding: 1.2rem 1rem;
  }

  .item {
    padding: 1rem;
    font-size: 0.88rem;
    line-height: 1.5;
  }
}
</style>
