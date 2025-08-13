<template>
  <div class="flex justify-center">
    <div class="glow">
      <img
          src="/images/minha_foto.png"
          alt="Minha Foto"
          class="w-full h-full object-cover rounded-xl opacity-100 brightness-100"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'GlowImage'
}
</script>

<style scoped>
.glow {
  border: 2px solid #3b82f6;
  border-radius: 1rem;
  position: relative;
  z-index: 10;
  animation: glow 2s ease-in-out infinite;
  width: 100%;
  height: 100%;
  overflow: hidden;
  aspect-ratio: 1 / 1;
  display: flex;
  align-items: center;
  justify-content: center;
}

@keyframes glow {
  0%, 100% {
    box-shadow: 0 0 15px #3b82f6, 0 0 30px #3b82f6;
    border-color: #3b82f6;
  }
  50% {
    box-shadow: 0 0 25px #60a5fa, 0 0 50px #60a5fa;
    border-color: #60a5fa;
  }
}

img {
  mix-blend-mode: normal;
  filter: contrast(1.1);
  transition: all 0.3s ease;
}

/* Responsividade do glow effect */
@media (max-width: 640px) {
  .glow {
    border-width: 1.5px;
  }

  @keyframes glow {
    0%, 100% {
      box-shadow: 0 0 10px #3b82f6, 0 0 20px #3b82f6;
    }
    50% {
      box-shadow: 0 0 15px #60a5fa, 0 0 30px #60a5fa;
    }
  }
}

@media (min-width: 641px) and (max-width: 768px) {
  .glow {
    border-width: 2px;
  }

  @keyframes glow {
    0%, 100% {
      box-shadow: 0 0 12px #3b82f6, 0 0 25px #3b82f6;
    }
    50% {
      box-shadow: 0 0 20px #60a5fa, 0 0 40px #60a5fa;
    }
  }
}

@media (min-width: 1024px) {
  .glow {
    border-width: 3px;
  }

  @keyframes glow {
    0%, 100% {
      box-shadow: 0 0 20px #3b82f6, 0 0 40px #3b82f6;
    }
    50% {
      box-shadow: 0 0 30px #60a5fa, 0 0 60px #60a5fa;
    }
  }
}

/* Hover effect para desktop */
@media (min-width: 1024px) {
  .glow:hover {
    transform: scale(1.05);
    transition: transform 0.3s ease;
  }

  .glow:hover img {
    filter: contrast(1.2) brightness(1.1);
  }
}
</style>