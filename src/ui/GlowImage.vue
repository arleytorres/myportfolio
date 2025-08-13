<template>
  <div class="flex justify-center mt-[-50px]">
    <div class="glow">
      <img
          src="../../public/images/minha_foto.png"
          alt="Minha Foto"
          class="w-70 h-70 rounded-xl opacity-100 brightness-100"
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
  border: 3px solid #3b82f6;
  border-radius: 1rem;
  position: relative;
  z-index: 10;
  animation: glow 2s ease-in-out infinite;
}

@keyframes glow {
  0%, 100% {
    box-shadow: 0 0 20px #3b82f6, 0 0 40px #3b82f6;
  }
  50% {
    box-shadow: 0 0 30px #60a5fa, 0 0 60px #60a5fa;
  }
}

img {
  mix-blend-mode: normal;
  filter: contrast(1.1);
}
</style>