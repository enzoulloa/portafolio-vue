<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-logo">Enzo Ulloa</div>

      <button class="navbar-toggle" @click="toggleMenu">
        <span :class="{ open: isOpen }"></span>
        <span :class="{ open: isOpen }"></span>
        <span :class="{ open: isOpen }"></span>
      </button>

      <div class="navbar-menu" :class="{ open: isOpen }">
        <ul>
          <li v-for="nav in navegacion" :key="nav.id">
            <a :href="nav.enlace" class="nav-item" @click="closeMenu">
              {{ nav.nombre }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const navegacion = ref([
  { id: 1, nombre: 'Educación', enlace: '#educacion' },
  { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Habilidades', enlace: '#habilidades' },
  { id: 5, nombre: 'Intereses', enlace: '#intereses' },
]);

const isOpen = ref(false);
const toggleMenu = () => (isOpen.value = !isOpen.value);
const closeMenu = () => (isOpen.value = false);
</script>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(29, 22, 22, 0.98);
  backdrop-filter: blur(10px);
  padding: 1rem 2rem;
  border-bottom: 2px solid #D84040;
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-logo {
  font-size: 1.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, #D84040, #8E1616);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

/* ===== BOTÓN HAMBURGUESA ===== */
.navbar-toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 25px;
  height: 18px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
}

.navbar-toggle span {
  height: 3px;
  width: 100%;
  background: #eeeeee;
  border-radius: 2px;
  transition: all 0.3s ease;
}

.navbar-toggle span.open:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.navbar-toggle span.open:nth-child(2) {
  opacity: 0;
}

.navbar-toggle span.open:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* ===== MENÚ ===== */
.navbar-menu {
  display: flex;
}

.navbar-menu ul {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
}

.nav-item {
  color: #eeeeee;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 500;
  position: relative;
  transition: color 0.3s ease;
}

.nav-item::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -5px;
  left: 0;
  background: #D84040;
  transition: width 0.3s ease;
}

.nav-item:hover {
  color: #D84040;
}

.nav-item:hover::after {
  width: 100%;
}

/* ===== RESPONSIVE ===== */
@media (max-width: 768px) {
  .navbar {
    padding: 0.75rem 1rem;
  }

  .navbar-toggle {
    display: flex;
  }

  .navbar-menu {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: rgba(29, 22, 22, 0.98);
    border-top: 2px solid #D84040;
    flex-direction: column;
    align-items: center;
    overflow: hidden;
    max-height: 0;
    transition: max-height 0.3s ease;
  }

  .navbar-menu.open {
    max-height: 300px;
  }

  .navbar-menu ul {
    flex-direction: column;
    gap: 1.2rem;
    padding: 1rem 0;
  }

  .navbar-logo {
    font-size: 1.2rem;
  }
}
</style>
