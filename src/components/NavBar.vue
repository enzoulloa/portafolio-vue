<template>
    <nav class='navbar'>
      <div class='navbar-container'>
        <div class='navbar-logo'>E.U</div>
        <div class='navbar-menu'>
          <ul>
              <a v-for="nav in navegacion" :key="nav.nombre" :href="nav.enlace" class="nav-item">
                {{ nav.nombre }}
              </a>
          </ul>
        </div>
      </div>
    </nav>
</template>

<script setup>
import { ref } from 'vue';

const navegacion = ref([
    {id:1, nombre:'Educación', enlace:'#educacion'},
    {id:2, nombre:'Experiencia', enlace:'#experiencia'},
    {id:3, nombre:'Proyectos', enlace:'#proyectos'},
    {id:4, nombre:'Habilidades', enlace:'#habilidades'}
])
</script>

<style scoped>
.navbar {
    position: sticky;
    top: 0;
    z-index: 1000;
    /* Fondo marrón oscuro con transparencia */
    background: rgba(29, 22, 22, 0.98);
    backdrop-filter: blur(10px);
    padding: 1rem 2rem;
    /* Borde inferior en rojo brillante */
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
    /* Logo en rojo brillante */
    background: linear-gradient(135deg, #D84040, #8E1616);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

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
    /* Texto en blanco claro */
    color: #EEEEEE;
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
    /* Subrayado hover en rojo brillante */
    background: #D84040;
    transition: width 0.3s ease;
}

.nav-item:hover {
    /* Hover con rojo brillante */
    color: #D84040;
}

.nav-item:hover::after {
    width: 100%;
}

@media (max-width: 768px) {
    .navbar {
        padding: 0.75rem 1rem;
    }

    .navbar-menu ul {
        gap: 1rem;
        font-size: 0.85rem;
    }

    .navbar-logo {
        font-size: 1.2rem;
    }
}
</style>
