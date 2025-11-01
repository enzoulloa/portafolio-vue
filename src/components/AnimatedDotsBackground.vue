<template>
  <div class="background-animation">
    <div class="particle" v-for="n in 80" :key="n" :style="{ 
      '--delay': (n * 0.05) + 's', 
      '--duration': (2 + Math.random() * 3) + 's',
      '--start-x': Math.random() * 100 + '%',
      '--offset-x': (Math.random() - 0.5) * 200 + 'px'
    }"></div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const particles = ref(Array.from({ length: 80 }));
</script>

<style scoped>
.background-animation {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: 0;
}

.particle {
  position: absolute;
  width: 6px;
  height: 6px;
  background: #D84040;
  border-radius: 50%;
  opacity: 0.7;
  animation: drift var(--duration) linear infinite;
  animation-delay: var(--delay);
  left: var(--start-x);
}

.particle:nth-child(odd) {
  background: #8E1616;
}

.particle:nth-child(3n) {
  background: #D84040;
  opacity: 0.4;
}

.particle:nth-child(4n) {
  background: #1D1616;
  opacity: 0.5;
}

@keyframes drift {
  0% {
    transform: translate(var(--offset-x), 100vh) rotate(0deg);
    opacity: 0;
  }
  5% {
    opacity: 0.7;
  }
  95% {
    opacity: 0.7;
  }
  100% {
    transform: translate(var(--offset-x), -100vh) rotate(360deg);
    opacity: 0;
  }
}

@media (max-width: 768px) {
  .particle {
    width: 4px;
    height: 4px;
  }
}
</style>
