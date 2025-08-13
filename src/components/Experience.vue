<template>
  <section id="experience" class="h-210 bg-[#080C17] w-full justify-center items-center text-white">
    <div class="container mx-auto px-17 relative">
      <div class="relative right-8">
        <div class="absolute w-0.5 bg-gray-600 h-165 mt-33 left-[7px]"></div>
        <div class="absolute rounded-full w-4 h-4 z-10 bg-cyan-500 shadow-2xl shadow-cyan-900/20 mt-39"></div>
      </div>
      <main class="grid md:grid-cols-1 gap-x-40">
        <h2 class="experiencia text-white mt-6">Experiência</h2>

        <ExperienceCards titulo="Gerador de Propostas Comerciais" data="Jun/2024 - Ago/2024" descricao="Um software desktop desenvolvido para otimizar o processo de elaboração de propostas de negócios,
         transformando o trabalho antes manual, em um trabalho mais interativo com base em interface" :tecnologias="geradorPropostas" />

        <ExperienceCards titulo="Integração InSim para Servidor" data="Mar/2024 - Abril/2024" descricao="Um software desktop para implementar funções no jogo Live For Speed" :tecnologias="integracaoInSim" />

        <ExperienceCards titulo="PDV Software" data="Mai/2023 - Jul/2023" descricao="Software desktop para gerenciamento interno de loja, proporcionando não somente a manipulação de clientes e produtos,
         mas também um controle total de acesso e seguraça." :tecnologias="pdvSoftware" />

        <experienceCards titulo="Bot Discord" data="Abri/2023 - Mai/2023" descricao="Um sistema de bot para automação e implementação de funções em comunidades na plataforma Discord" :tecnologias="botDiscord" />
      </main>
    </div>
  </section>
</template>

<script>
import ExperienceCards from "@/ui/ExperienceCards.vue";
export default {
  name: 'Experience',
  components:{
    ExperienceCards
  },
  data:() => ({
    integracaoInSim:[
      {name: 'C#'},
      {name: '.Net Framework'},
      {name: 'SQLite'},
      {name: 'InSimDotNet'},
      {name: 'Newtonsoft'}
    ],
    geradorPropostas:[
      {name: 'C#'},
      {name: '.Net Framework'},
      {name: 'WindowsForms'},
      {name: 'Microsoft.Office'}
    ],
    pdvSoftware:[
      {name: 'C#'},
      {name: '.Net Framework'},
      {name: 'WindowsForms'},
      {name: 'SQLite'},
      {name: 'EntityFrameworkCore'},
      {name: 'MercadoPagoSDK'},
      {name: 'Newtonsoft'}
    ],
    botDiscord:[
      {name: 'C#'},
      {name: '.NetCore'},
      {name: 'MySQL'},
      {name: 'DSharpPlus'},
      {name: 'Newtonsoft'}
    ]
  })
}
</script>

<style scoped>
@import "tailwindcss";
.experiencia{
  font-family: 'Playfair Display', serif;
  font-size: 36px;
}
</style>