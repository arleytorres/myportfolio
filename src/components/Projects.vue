<template>
  <section id="project" class="min-h-screen bg-[#080C17] w-full py-20">
    <div class="container mx-auto px-4 md:px-17">
      <h2 class="projetos text-white font-bold mb-6 mt-15">Projetos</h2>
      <div class="grid md:grid-cols-2 gap-8">
        <ProjectsCards
            imagem="foto_voxer.png"
            titulo="VOXER - Plataforma de Comunicação"
            data="Abri/2025 - Jun/2025"
            descricao="Uma aplicação de comunicação para desktop baseada em aplicações como: Raidcall, Discord, TeamSpeak. Sendo capaz de criar comunidades, canais de texto e até canais de voz."
            :buttom= false
            :tecnologias="voxerTecnologias"
        />
        <ProjectsCards
            imagem="imagem_clean-Cache.png"
            titulo="Clean Cache"
            data="Mar/2025 - Abri/2025"
            descricao="Uma aplicação desktop para limpeza e otimização do sistema."
            :buttom= true
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
  font-size: 36px;
}
</style>