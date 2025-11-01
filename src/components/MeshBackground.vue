<template>
  <div class="fondo-animado">
    <div class="gradiente g1"></div>
    <div class="gradiente g2"></div>
    <div class="gradiente g3"></div>
    <div class="malla"></div>
  </div>
</template>

<style scoped>
.fondo-animado {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  overflow: hidden;
  background: #1D1616;
}

.gradiente {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  mix-blend-mode: screen;
}

@keyframes fluir-g1 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(100px, -50px) scale(1.2); }
}

@keyframes fluir-g2 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(-80px, 60px) scale(1.1); }
}

@keyframes fluir-g3 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(60px, 40px) scale(1.15); }
}

.g1 {
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, #D84040, transparent);
  top: -100px;
  left: -100px;
  opacity: 0.4;
  animation: fluir-g1 10s ease-in-out infinite;
}

.g2 {
  width: 350px;
  height: 350px;
  background: radial-gradient(circle, #8E1616, transparent);
  top: 50%;
  right: -50px;
  opacity: 0.3;
  animation: fluir-g2 12s ease-in-out infinite;
}

.g3 {
  width: 380px;
  height: 380px;
  background: radial-gradient(circle, #D84040, transparent);
  bottom: -100px;
  left: 30%;
  opacity: 0.35;
  animation: fluir-g3 14s ease-in-out infinite;
}

.malla {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: 
    linear-gradient(0deg, transparent 24%, rgba(216, 64, 64, 0.05) 25%, rgba(216, 64, 64, 0.05) 26%, transparent 27%, transparent 74%, rgba(216, 64, 64, 0.05) 75%, rgba(216, 64, 64, 0.05) 76%, transparent 77%, transparent),
    linear-gradient(90deg, transparent 24%, rgba(216, 64, 64, 0.05) 25%, rgba(216, 64, 64, 0.05) 26%, transparent 27%, transparent 74%, rgba(216, 64, 64, 0.05) 75%, rgba(216, 64, 64, 0.05) 76%, transparent 77%, transparent);
  background-size: 60px 60px;
}

@media (max-width: 768px) {
  .g1 { width: 250px; height: 250px; }
  .g2 { width: 200px; height: 200px; }
  .g3 { width: 230px; height: 230px; }
}
</style>
