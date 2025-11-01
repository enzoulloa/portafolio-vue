<script setup>
import linkedin from '/src/assets/linkedin.svg';
import instagram from '/src/assets/instagram.svg';
import github from '/src/assets/github.svg';
import phone from '/src/assets/smartphone.svg';
// import cv from '/src/assets/cv_resume_icon.svg';

const title = 'Enzo Ulloa';
const descripcion = 'Técnico Universitario en Programación';
const residencia = 'Godoy Cruz, Mendoza, Argentina';
const presentacion = '👨‍💻 Soy Enzo, apasionado por la tecnología y siempre en búsqueda de nuevos desafíos. 👾 Responsable, autocrítico y orientado al crecimiento continuo. 🚀 Me encanta resolver problemas complejos con código elegante y escalable.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin, url: '' },
  { id: 2, name: 'Instagram', src: instagram, url: '' },
  { id: 3, name: 'github', src: github, url: 'https://github.com/enzoulloa' },
//   { id: 4, name: 'curriculum', src: cv, url: '' },
];
const telefono = '2616337108';
</script>

<template>
  <section class="datos-personales">
    <div class="hero-container">
      <div class="hero-content">
        <h1 class="hero-title">{{ title }}</h1>
        <h2 class="hero-subtitle">{{ descripcion }}</h2>
        <p class="hero-description">{{ presentacion }}</p>
        <ul class="container-lista">
          <li v-for="red in redesSociales" :key="red.id">
            <a :href="red.url" class="social-icon" :title="red.name">
              <img :src="red.src" width="24" :alt="red.name">
            </a>
          </li>
        </ul>
        <div class="hero-footer">
          <span class="location">📍 {{ residencia }}</span>
          <span class="phone"><img :src="phone" width="24" alt="phone number"> {{ telefono }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.datos-personales {
    /* Fondo con gradiente de marrón a rojo */
    background: linear-gradient(135deg, #1D1616 0%, #2a1f1f 50%, #8E1616 100%);
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 4rem 2rem;
    position: relative;
    overflow: hidden;
}

.datos-personales::before {
    content: '';
    position: absolute;
    width: 400px;
    height: 400px;
    /* Efecto de brillo en rojo brillante */
    background: radial-gradient(circle, rgba(216, 64, 64, 0.15) 0%, transparent 70%);
    border-radius: 50%;
    top: -100px;
    right: -100px;
}

.hero-container {
    max-width: 900px;
    margin: 0 auto;
    position: relative;
    z-index: 1;
}

.hero-content {
    animation: slideUp 0.8s ease-out;
}

@keyframes slideUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.hero-title {
    font-size: 3.5rem;
    font-weight: 800;
    /* Gradiente con colores de la paleta -->
    background: linear-gradient(135deg, #EEEEEE, #D84040);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 0.5rem;
    line-height: 1.2;
}

.hero-subtitle {
    font-size: 1.5rem;
    /* Texto en rojo brillante */
    color: #D84040;
    font-weight: 400;
    margin-bottom: 1.5rem;
}

.hero-description {
    font-size: 1.1rem;
    /* Texto en blanco claro */
    color: #EEEEEE;
    line-height: 1.8;
    margin-bottom: 2rem;
    max-width: 600px;
}

.container-lista {
    display: flex;
    list-style: none;
    padding: 0;
    margin: 0 0 2rem 0;
    gap: 1rem;
}

.social-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
   
    background: rgba(216, 64, 64, 0.15);
    border: 2px solid rgba(216, 64, 64, 0.4);
    border-radius: 10px;
    transition: all 0.3s ease;
    cursor: pointer;
}

.social-icon:hover {
 
    background: rgba(216, 64, 64, 0.3);
    border-color: #D84040;
    transform: translateY(-3px);
    box-shadow: 0 0 15px rgba(216, 64, 64, 0.4);
}

.social-icon img {
    filter: brightness(0) invert(1);
    opacity: 0.8;
    transition: opacity 0.3s ease;
}

.social-icon:hover img {
    opacity: 1;
}

.hero-footer {
    display: flex;
    gap: 2rem;
    font-size: 0.95rem;
    color: #EEEEEE;
    margin-top: 2rem;
}

.location, .phone {
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

@media (max-width: 768px) {
    .hero-title {
        font-size: 2.5rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }

    .hero-description {
        font-size: 1rem;
    }

    .hero-footer {
        flex-direction: column;
        gap: 1rem;
    }
}
</style>
