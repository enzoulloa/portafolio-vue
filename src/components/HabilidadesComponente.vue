<script setup>
import img1 from '/src/components/icons/js.svg';
import img2 from '/src/components/icons/python.svg';
import img3 from '/src/components/icons/html-css.svg';
import img4 from '/src/components/icons/java.svg';
import img5 from '/src/components/icons/sql.svg';
import img6 from '/src/components/icons/react.svg';
import img7 from '/src/components/icons/vue.svg';
import img8 from '/src/components/icons/node.svg';
import img9 from '/src/components/icons/django.svg';
import img10 from '/src/components/icons/bootstrap.svg';
import img11 from '/src/components/icons/git.svg';
import img12 from '/src/components/icons/docker.svg';
import img13 from '/src/components/icons/cypress.svg';
import img14 from '/src/components/icons/figma.svg';
import img15 from '/src/components/icons/visual.svg';
import img16 from '/src/components/icons/mongo.svg';
import img17 from '/src/components/icons/mysql.svg';
import img18 from '/src/components/icons/postgres.svg';
import img19 from '/src/components/icons/arg.svg';
import img20 from '/src/components/icons/eeuu.svg';

// ⚠️ Podés agregar íconos faltantes si los tenés (por ej. Tailwind, Redux, NestJS, etc.)
// y actualizar las rutas, pero igual los incluyo en la lista aunque no tengan ícono aún.

import { ref } from 'vue';

const habilidades = ref([
  {
    id: 1,
    nombre: 'Lenguajes de Programación',
    habilidades: [
      { id: 1, nombre: 'JavaScript', nivel: 'Avanzado', icono: img1 },
      { id: 2, nombre: 'TypeScript', nivel: 'Intermedio', icono: img1 },
      { id: 3, nombre: 'Python', nivel: 'Intermedio', icono: img2 },
      { id: 4, nombre: 'Java', nivel: 'Intermedio', icono: img4 },
      { id: 5, nombre: 'HTML5', nivel: 'Avanzado', icono: img3 },
      { id: 6, nombre: 'CSS3 / Sass', nivel: 'Avanzado', icono: img3 }
    ]
  },
  {
    id: 2,
    nombre: 'Frameworks y Librerías',
    habilidades: [
      { id: 1, nombre: 'React.js', nivel: 'Avanzado', icono: img6 },
      { id: 2, nombre: 'Redux', nivel: 'Avanzado', icono: img6 },
      { id: 3, nombre: 'React Router', nivel: 'Avanzado', icono: img6 },
      { id: 4, nombre: 'React Query', nivel: 'Avanzado', icono: img6 },
      { id: 5, nombre: 'Next.js', nivel: 'Intermedio', icono: img6 },
      { id: 6, nombre: 'TailwindCSS', nivel: 'Avanzado', icono: img10 },
      { id: 7, nombre: 'Node.js', nivel: 'Avanzado', icono: img8 },
      { id: 8, nombre: 'Express', nivel: 'Avanzado', icono: img8 },
      { id: 9, nombre: 'NestJS', nivel: 'Intermedio', icono: img8 },
      { id: 10, nombre: 'Vue.js', nivel: 'Intermedio', icono: img7 },
      { id: 11, nombre: 'Django', nivel: 'Intermedio', icono: img9 },
      { id: 12, nombre: 'Bootstrap', nivel: 'Avanzado', icono: img10 },
      { id: 13, nombre: 'Socket.io', nivel: 'Intermedio', icono: img8 }
    ]
  },
  {
    id: 3,
    nombre: 'Bases de Datos y ORM',
    habilidades: [
      { id: 1, nombre: 'PostgreSQL', nivel: 'Avanzado', icono: img18 },
      { id: 2, nombre: 'MySQL', nivel: 'Intermedio', icono: img17 },
      { id: 3, nombre: 'MongoDB', nivel: 'Avanzado', icono: img16 },
      { id: 4, nombre: 'Sequelize', nivel: 'Intermedio', icono: img5 },
      { id: 5, nombre: 'Prisma ORM', nivel: 'Intermedio', icono: img5 }
    ]
  },
  {
    id: 4,
    nombre: 'Herramientas y Ecosistema',
    habilidades: [
      { id: 1, nombre: 'Git', nivel: 'Avanzado', icono: img11 },
      { id: 2, nombre: 'npm / pnpm', nivel: 'Avanzado', icono: img11 },
      { id: 3, nombre: 'Vite.js', nivel: 'Avanzado', icono: img6 },
      { id: 4, nombre: 'Docker', nivel: 'Intermedio', icono: img12 },
      { id: 5, nombre: 'Cypress', nivel: 'Intermedio', icono: img13 },
      { id: 6, nombre: 'Google Cloud', nivel: 'Intermedio', icono: img12 },
      { id: 7, nombre: 'Figma / Design System', nivel: 'Intermedio', icono: img14 },
      { id: 8, nombre: 'Visual Studio Code', nivel: 'Avanzado', icono: img15 },
      { id: 9, nombre: 'Scrum / Metodologías Ágiles', nivel: 'Intermedio', icono: img15 }
    ]
  },
  {
    id: 5,
    nombre: 'Idiomas',
    habilidades: [
      { id: 1, nombre: 'Español', nivel: 'Nativo', icono: img19 },
      { id: 2, nombre: 'Inglés', nivel: 'Intermedio (B2)', icono: img20 }
    ]
  }
]);
</script>

<template>
  <div class="skills-contenedor">
    <div v-for="categoria in habilidades" :key="categoria.id" class="skills-categoria">
      <h3>{{ categoria.nombre }}</h3>
      <ul class="skills">
        <li v-for="skill in categoria.habilidades" :key="skill.id" class="skill">
          <img :src="skill.icono" :alt="skill.nombre" />
          <span>{{ skill.nombre }}: {{ skill.nivel }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.skills-contenedor {
  padding: 2rem;
  background: linear-gradient(-45deg, #021526, #03346e, #6eacda, #e2e2b6);
}

.skills-categoria {
  margin-bottom: 20px;
}

.skills-categoria h3 {
  margin-bottom: 10px;
  font-size: 1.5em;
  color: aliceblue;
  font-weight: bold;
}

.skills {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  gap: 20px;
}

.skill {
  display: flex;
  align-items: center;
  gap: 10px;
  background-color: rgba(241, 245, 243, 0.856);
  padding: 0.3em;
  border-radius: 8px;
  box-shadow: 0px 4px 12px rgba(2, 151, 151, 0.963);
  flex: 1 1 200px;
  max-width: 250px;
  transition: background-color 0.3s ease;
}

.skill:hover {
  background-color: rgba(2, 151, 151, 0.963);
  transform: scale(1.03);
}

.skill img {
  width: 35px;
  height: 35px;
}

.skill span {
  font-size: 1em;
  color: #333;
}

@media (max-width: 768px) {
  .skills-categoria h3 {
    text-align: center;
  }
}
</style>
