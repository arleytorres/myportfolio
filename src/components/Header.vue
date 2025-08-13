<template>
  <header class="flex fixed top-0 w-full z-50 h-16 items-center justify-center bg-gray-900/30 backdrop-blur-sm border-b-1 border-gray-700">
    <div class="grid md:grid-cols-3 w-full items-center text-gray-300 text-[14px]">
      <div>
        <a href="#hero"><p class="font-bold hover:scale-110 transition-transform
        text-center text-white text-[16px] cursor-pointer">Arley_Torres</p></a>
      </div>
      <div class="flex-1 flex flex-row items-center justify-center gap-6">
        <a href="#hero"><p class="hover:text-white cursor-pointer">Início</p></a>
        <a href="#about"><p class="hover:text-white cursor-pointer">Sobre</p></a>
        <a href="#skills"><p class="hover:text-white cursor-pointer">Skills</p></a>
        <a href="#experience"><p class="hover:text-white cursor-pointer">Experiência</p></a>
        <a href="#project"><p class="hover:text-white cursor-pointer">Projetos</p></a>
        <a href="#contact"><p class="hover:text-white cursor-pointer">Contato</p></a>
      </div>
      <div class="font-sans text-center text-gray-300">
        <a href="#project"><p class="hover:text-white hover:underline cursor-pointer">Ver Projetos</p></a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>