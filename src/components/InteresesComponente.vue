<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue';

// Arreglo reactivo con los nuevos intereses
const intereses = ref([
    'Tecnología: Me apasiona mantenerme al día con las últimas innovaciones, aprender nuevos lenguajes y explorar tendencias como la inteligencia artificial y el desarrollo web moderno.',
    'Fútbol: Disfruto mirar y jugar al fútbol, siguiendo las principales ligas y torneos, y compartiendo la pasión por este deporte con amigos.',
    'E-sports: Me interesa el mundo competitivo de los videojuegos, especialmente títulos como Counter Strike y otros juegos de estrategia en equipo.',
    'Viajes: Me gusta conocer nuevos lugares, culturas y comidas, aprovechando cada viaje como una oportunidad de aprendizaje y desconexión.'
]);
</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava />
        <ul class="contenedor-lista">
            <li class="item" v-for="interes in intereses" :key="interes">
                {{ interes }}
            </li>
        </ul>
    </div>
        <!-- <div class="intereses-contenedor">
        <ul class="contenedor-lista">
            <li class="item">
                Desarrollo de Software de Código Abierto: Contribuyo a proyectos en GitHub, colaborando con otros
                desarrolladores para mejorar herramientas y librerías populares.
            </li>
            <li class="item">
                Deportes al Aire Libre: Disfruto del senderismo y el ciclismo de montaña, actividades que practico
                regularmente para mantener un equilibrio entre el trabajo y la vida personal.
            </li>
            <li class="item">
                Tecnología de Innovación: Me apasiona explorar nuevas tendencias tecnológicas como la inteligencia
                artificial y el desarrollo de aplicaciones móviles.
            </li>
            <li class="item">
                Fotografía: Practico la fotografía como un hobby, lo que me ayuda a mantener una perspectiva creativa
                tanto en mi vida profesional como personal.
            </li>
        </ul>
    </div> -->
</template>

<style scoped>
.intereses-contenedor {
    display: flex;
    position: relative;
    margin: 0 auto;
    max-width: 85%;
    padding: 1rem;
}

.contenedor-lista {
    list-style-type: none;
    padding: 1rem;
    margin-bottom: 0.5rem;
    color: var(--vt-c-white-soft);
    font-size: 1.4rem;
    text-shadow: 3px 3px 6px rgba(0, 0, 0, 1);
}

.item {
    margin-bottom: 1rem;
}
</style>
