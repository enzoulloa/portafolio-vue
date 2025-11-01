<script setup>
import appish from '/src/assets/appish.png';
import happy from '/src/assets/happy.png';
import hunter from '/src/assets/hunter.png';
import { ref } from 'vue';

const misProyectos = ref([
  {
    id: 1,
    src: appish,
    titulo: "Appish",
    descripcion:
      "Appish es una página hecha para practicar teniendo como referencia a webflow.com. Usando buenas prácticas y cuidando el SEO y el performance.",
    tech: "Tech stack: React, TailwindCSS.",
    projectoLink: "https://main--ubiquitous-sopapillas-c4e681.netlify.app/",
    githubLink: "https://github.com/usuario/appish",
  },
  {
    id: 2,
    src: happy,
    titulo: "Happy",
    descripcion:
      "Happy es una página hecha para practicar teniendo como referencia a webflow.com. Usando buenas prácticas y cuidando el SEO y el performance.",
    tech: "Tech stack: React, TailwindCSS.",
    projectoLink: "https://main--ubiquitous-sopapillas-c4e681.netlify.app/",
    githubLink: "https://github.com/usuario/happy",
  },
  {
    id: 3,
    src: hunter,
    titulo: "Hunter",
    descripcion:
      "Hunter es una página hecha para practicar teniendo como referencia a webflow.com.",
    tech: "Tech stack: React, TailwindCSS.",
    projectoLink: "https://tangerine-bublanina-840fb9.netlify.app/",
    githubLink: "https://github.com/usuario/hunter",
  },
]);
</script>

<template>
  <section id="proyectos" class="galeria">
    <li class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
      <img :src="proyecto.src" :alt="proyecto.titulo" class="proyecto-img" />
      <div class="proyecto-info">
        <h3>{{ proyecto.titulo }}</h3>
        <p>{{ proyecto.descripcion }}</p>
        <p style="color: #94a3b8; font-size: 0.85rem; margin-bottom: 1rem;">
          {{ proyecto.tech }}
        </p>
        <div class="proyecto-links">
          <a
            :href="proyecto.projectoLink"
            class="btn-ver-mas"
            target="_blank"
            rel="noopener noreferrer"
          >
            Ver Proyecto
          </a>
          <a
            :href="proyecto.githubLink"
            class="github-link"
            target="_blank"
            rel="noopener noreferrer"
          >
            GitHub
          </a>
        </div>
      </div>
    </li>
  </section>
</template>

<style scoped>
.galeria {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
  list-style: none;
}

.proyecto {
  display: flex;
  flex-direction: column;
  background: rgba(15, 23, 42, 0.6);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  overflow: hidden;
  transition: all 0.3s ease;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
}

.proyecto:hover {
  transform: translateY(-8px);
  border-color: rgba(0, 212, 255, 0.3);
  background: rgba(15, 23, 42, 0.8);
  box-shadow: 0 12px 40px rgba(0, 212, 255, 0.15);
}

.proyecto-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.proyecto:hover .proyecto-img {
  transform: scale(1.05);
}

.proyecto-info {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.proyecto-info h3 {
  font-size: 1.1rem;
  color: #e0e7ff;
  margin: 0 0 0.75rem 0;
  font-weight: 600;
}

.proyecto-info p {
  color: #cbd5e1;
  font-size: 0.9rem;
  line-height: 1.5;
  margin-bottom: 1.5rem;
  flex: 1;
}

.proyecto-links {
  display: flex;
  gap: 1rem;
}

.btn-ver-mas {
  flex: 1;
  background: linear-gradient(135deg, #00d4ff, #0099ff);
  color: #0f172a;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  text-decoration: none;
  text-align: center;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.btn-ver-mas:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0, 212, 255, 0.3);
}

.github-link {
  flex: 1;
  color: #00d4ff;
  border: 1px solid rgba(0, 212, 255, 0.3);
  padding: 0.75rem 1rem;
  border-radius: 8px;
  text-decoration: none;
  text-align: center;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  background: transparent;
}

.github-link:hover {
  background: rgba(0, 212, 255, 0.1);
  border-color: #00d4ff;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .galeria {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    padding: 1rem;
  }

  .proyecto-info {
    padding: 1rem;
  }
}
</style>
