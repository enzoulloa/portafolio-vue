<script setup>
import javaScriptIcon from '/src/components/icons/js.svg';
import pythonIcon from '/src/components/icons/python.svg';
import htmlIcon from '/src/components/icons/html-css.svg';
import javaIcon from '/src/components/icons/java.svg';
import sqlIcon from '/src/components/icons/sql.svg';
import reactIcon from '/src/components/icons/react.svg';
import vueIcon from '/src/components/icons/vue.svg';
import nodeIcon from '/src/components/icons/node.svg';
import djangoIcon from '/src/components/icons/django.svg';
import bootstrapIcon from '/src/components/icons/bootstrap.svg';
import gitIcon from '/src/components/icons/git.svg';
import dockerIcon from '/src/components/icons/docker.svg';
import cypressIcon from '/src/components/icons/cypress.svg';
import figmaIcon from '/src/components/icons/figma.svg';
import visualIcon from '/src/components/icons/visual.svg';
import mongoIcon from '/src/components/icons/mongo.svg';
import mySqlIcon from '/src/components/icons/mysql.svg';
import postgresIcon from '/src/components/icons/postgres.svg';
import argentinaIcon from '/src/components/icons/argentina.svg';
import cssIcon from '/src/components/icons/css.svg';
import tsIcon from '/src/components/icons/ts.svg';
import englishIcon from '/src/components/icons/english.svg';
import expressIcon from '/src/components/icons/express.svg';
import prismaIcon from '/src/components/icons/prisma.svg';
import reduxIcon from '/src/components/icons/redux.svg';
import nextIcon from '/src/components/icons/next.svg';
import tailwindIcon from '/src/components/icons/tailwind.svg';
import socketIcon from '/src/components/icons/socket-dot-io.svg';
import npmIcon from '/src/components/icons/npm.svg';
import googleCloudIcon from '/src/components/icons/google-cloud.svg';
import nestJsIcon from '/src/components/icons/nestjs.svg';
import scrumIcon from '/src/components/icons/scrum.svg';
import reactRouterIcon from '/src/components/icons/react-router.svg';
import sequelizeIcon from '/src/components/icons/sequelize.svg';
import viteIcon from '/src/components/icons/vitejs.svg';
import codeIcon from '/src/assets/code.svg';

import { ref } from 'vue';

const habilidades = ref([
  {
    id: 1,
    nombre: 'Lenguajes de Programación',
    habilidades: [
      { id: 1, nombre: 'JavaScript', nivel: 'Avanzado', icono: javaScriptIcon },
      { id: 2, nombre: 'TypeScript', nivel: 'Intermedio', icono: tsIcon },
      { id: 3, nombre: 'Python', nivel: 'Intermedio', icono: pythonIcon },
      { id: 4, nombre: 'Java', nivel: 'Intermedio', icono: javaIcon },
      { id: 5, nombre: 'HTML5', nivel: 'Avanzado', icono: htmlIcon },
      { id: 6, nombre: 'CSS3 / Sass', nivel: 'Avanzado', icono: cssIcon },
      { id: 7, nombre: 'SQL', nivel: 'Intermedio', icono: sqlIcon }
    ]
  },
  {
    id: 2,
    nombre: 'Frameworks y Librerías',
    habilidades: [
      { id: 1, nombre: 'React.js', nivel: 'Avanzado', icono: reactIcon },
      { id: 2, nombre: 'Redux', nivel: 'Avanzado', icono: reduxIcon },
      { id: 3, nombre: 'React Router', nivel: 'Avanzado', icono: reactRouterIcon },
      { id: 4, nombre: 'React Query', nivel: 'Avanzado', icono: codeIcon },
      { id: 5, nombre: 'Next.js', nivel: 'Intermedio', icono: nextIcon },
      { id: 6, nombre: 'TailwindCSS', nivel: 'Avanzado', icono: tailwindIcon },
      { id: 7, nombre: 'Node.js', nivel: 'Avanzado', icono: nodeIcon },
      { id: 8, nombre: 'Express', nivel: 'Avanzado', icono: expressIcon },
      { id: 9, nombre: 'NestJS', nivel: 'Intermedio', icono: nestJsIcon },
      { id: 10, nombre: 'Vue.js', nivel: 'Intermedio', icono: vueIcon },
      { id: 11, nombre: 'Django', nivel: 'Intermedio', icono: djangoIcon },
      { id: 12, nombre: 'Bootstrap', nivel: 'Avanzado', icono: bootstrapIcon },
      { id: 13, nombre: 'Socket.io', nivel: 'Intermedio', icono: socketIcon }
    ]
  },
  {
    id: 3,
    nombre: 'Bases de Datos y ORM',
    habilidades: [
      { id: 1, nombre: 'PostgreSQL', nivel: 'Avanzado', icono: postgresIcon },
      { id: 2, nombre: 'MySQL', nivel: 'Intermedio', icono: mySqlIcon },
      { id: 3, nombre: 'MongoDB', nivel: 'Avanzado', icono: mongoIcon },
      { id: 4, nombre: 'Sequelize', nivel: 'Intermedio', icono: sequelizeIcon },
      { id: 5, nombre: 'Prisma ORM', nivel: 'Intermedio', icono: prismaIcon }
    ]
  },
  {
    id: 4,
    nombre: 'Herramientas y Ecosistema',
    habilidades: [
      { id: 1, nombre: 'Git', nivel: 'Avanzado', icono: gitIcon },
      { id: 2, nombre: 'npm / pnpm', nivel: 'Avanzado', icono: npmIcon },
      { id: 3, nombre: 'Vite.js', nivel: 'Avanzado', icono: viteIcon },
      { id: 4, nombre: 'Docker', nivel: 'Intermedio', icono: dockerIcon },
      { id: 5, nombre: 'Cypress', nivel: 'Intermedio', icono: cypressIcon },
      { id: 6, nombre: 'Google Cloud', nivel: 'Intermedio', icono: googleCloudIcon },
      { id: 7, nombre: 'Figma / Design System', nivel: 'Intermedio', icono: figmaIcon },
      { id: 8, nombre: 'Visual Studio Code', nivel: 'Avanzado', icono: visualIcon },
      { id: 9, nombre: 'Scrum / Metodologías Ágiles', nivel: 'Intermedio', icono: scrumIcon }
    ]
  },
  {
    id: 5,
    nombre: 'Idiomas',
    habilidades: [
      { id: 1, nombre: 'Español', nivel: 'Nativo', icono: argentinaIcon },
      { id: 2, nombre: 'Inglés', nivel: 'Intermedio (B2)', icono: englishIcon }
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
  border-radius: 12px;
  padding: 3rem 2rem;
  background: rgba(29, 22, 22, 0.7);
  backdrop-filter: blur(10px);
}

.skills-categoria {
  max-width: 1200px;
  margin: 2rem auto 0;
}

.skills-categoria h3 {
  font-size: 1.6rem;
  color: #00d4ff;
  margin-bottom: 1.5rem;
  font-weight: 700;
  text-align: left;
}

.skills {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1.5rem;
  list-style: none;
  padding: 0;
  margin: 0 0 2rem 0;
}

.skill {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  background: rgba(0, 212, 255, 0.08);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 0.75rem 1.25rem;
  border-radius: 10px;
  transition: all 0.3s ease;
  min-width: 200px;
  justify-content: center;
}

.skill:hover {
  background: rgba(0, 212, 255, 0.15);
  border-color: rgba(0, 212, 255, 0.5);
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0, 212, 255, 0.2);
}

.skill img {
  width: 32px;
  height: 32px;
  filter: brightness(0) invert(1);
  opacity: 0.7;
  transition: all 0.3s ease;
}

.skill:hover img {
  opacity: 1;
  filter: brightness(0) invert(1) drop-shadow(0 0 5px #00d4ff);
}

.skill span {
  font-size: 0.95rem;
  color: #cbd5e1;
  font-weight: 500;
}

/* Tablet */
@media (max-width: 768px) {
  .skills-categoria h3 {
    text-align: center;
  }

  .skills {
    gap: 1rem;
  }

  .skill {
    flex-direction: column;
    text-align: center;
    min-width: 140px;
    max-width: 180px;
  }

  .skill span {
    font-size: 0.9rem;
  }
}

/* Mobile pequeño */
@media (max-width: 480px) {
  .skills-contenedor {
    padding: 2rem 1rem;
  }

  .skill {
    min-width: auto;
    max-width: 100%;
    padding: 0.6rem 1rem;
    gap: 0.5rem;
  }

  .skill img {
    width: 28px;
    height: 28px;
  }

  .skill span {
    font-size: 0.85rem;
  }
}
</style>
