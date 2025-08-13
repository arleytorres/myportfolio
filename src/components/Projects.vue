<template>
  <section id="project" class="min-h-screen bg-[#080C17] w-full flex justify-center items-center py-8 sm:py-12 md:py-16 lg:py-20">
    <div class="container mx-auto px-7 sm:7 md:px-7 lg:px-7 xl:px-7 relative">
      <!-- Título responsivo -->
      <h2 class="projetos text-white text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl mb-6 sm:mb-8 md:mb-10 lg:mb-12 lg:text-left">
        Projetos
      </h2>

      <!-- Grid responsivo dos cards -->
      <div class="grid grid-cols-1 xl:grid-cols-2 gap-6 sm:gap-8 md:gap-10 lg:gap-12 xl:gap-7 w-full">
        <ProjectsCards
            class="w-full"
            imagem="foto_voxer.png"
            titulo="VOXER - Plataforma de Comunicação"
            data="Abr/2025 - Jun/2025"
            descricao="Uma aplicação de comunicação para desktop baseada em aplicações como: Raidcall, Discord, TeamSpeak. Sendo capaz de criar comunidades, canais de texto e até canais de voz."
            :buttom="false"
            :tecnologias="voxerTecnologias"
        />

        <ProjectsCards
            class="w-full"
            imagem="imagem_clean-Cache.png"
            titulo="Clean Cache"
            data="Mar/2025 - Abr/2025"
            descricao="Uma aplicação desktop para limpeza e otimização do sistema."
            :buttom="true"
            linkPassado="https://github.com/arleytorres/Clean-Cache"
            :tecnologias="cleanCacheTecnologias"
        />
      </div>
    </div>
  </section>
</template>

<script>
import ProjectsCards from "../ui/ProjectsCards.vue";

export default {
  name: 'Projects',
  components: {
    ProjectsCards
  },
  data() {
    return {
      voxerTecnologias: [
        { name: "C#" },
        { name: ".Net 9.0" },
        { name: "WindowsForms" },
        { name: "SQLite" },
        { name: "UDP" },
        { name: "TCP" },
        { name: "SignalR" },
        { name: "Entity Framework Core" },
        { name: "MVVM" },
        { name: "GitHub" }
      ],
      cleanCacheTecnologias: [
        { name: "C#" },
        { name: ".Net Framework" },
        { name: "WindowsForms" }
      ]
    }
  }
}
</script>

<style scoped>
.projetos {
  font-family: 'Playfair Display', serif;
}

/* Breakpoints personalizados para tipografia */
@media (max-width: 480px) {
  .projetos {
    font-size: 28px;
  }
}

@media (min-width: 481px) and (max-width: 768px) {
  .projetos {
    font-size: 32px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .projetos {
    font-size: 40px;
  }
}

@media (min-width: 1025px) {
  .projetos {
    font-size: 48px;
  }
}
</style>