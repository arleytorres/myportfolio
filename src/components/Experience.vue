<template>
  <section id="experience" class="min-h-screen bg-[#080C17] w-full flex justify-center items-center text-white py-8 sm:py-12 md:py-16 lg:py-20">
    <div class="container mx-auto px-4 sm:px-6 md:px-8 lg:px-12 xl:px-7 relative w-full">

      <main class="grid grid-cols-1 gap-6 sm:gap-8 md:gap-10 lg:gap-12">
        <!-- Título responsivo -->
        <h2 class="experiencia text-white text-2xl sm:text-3xl lg:text-4xl lg:text-left -mb-7">
          Experiência
        </h2>

        <!-- Cards com espaçamento responsivo -->
        <div class="space-y-6 sm:space-y-6 md:space-y-6 lg:space-y-6">
          <ExperienceCards
              titulo="Gerador de Propostas Comerciais"
              data="Jun/2024 - Ago/2024"
              descricao="Um software desktop desenvolvido para otimizar o processo de elaboração de propostas de negócios, transformando o trabalho antes manual, em um trabalho mais interativo com base em interface"
              :tecnologias="geradorPropostas"
          />

          <ExperienceCards
              titulo="Integração InSim para Servidor"
              data="Mar/2024 - Abril/2024"
              descricao="Um software desktop para implementar funções no jogo Live For Speed"
              :tecnologias="integracaoInSim"
          />

          <ExperienceCards
              titulo="PDV Software"
              data="Mai/2023 - Jul/2023"
              descricao="Software desktop para gerenciamento interno de loja, proporcionando não somente a manipulação de clientes e produtos, mas também um controle total de acesso e segurança."
              :tecnologias="pdvSoftware"
          />

          <ExperienceCards
              titulo="Bot Discord"
              data="Abr/2023 - Mai/2023"
              descricao="Um sistema de bot para automação e implementação de funções em comunidades na plataforma Discord"
              :tecnologias="botDiscord"
          />
        </div>
      </main>
    </div>
  </section>
</template>

<script>
import ExperienceCards from "@/ui/ExperienceCards.vue";

export default {
  name: 'Experience',
  components: {
    ExperienceCards
  },
  data: () => ({
    integracaoInSim: [
      { name: 'C#' },
      { name: '.Net Framework' },
      { name: 'SQLite' },
      { name: 'InSimDotNet' },
      { name: 'Newtonsoft' }
    ],
    geradorPropostas: [
      { name: 'C#' },
      { name: '.Net Framework' },
      { name: 'WindowsForms' },
      { name: 'Microsoft.Office' }
    ],
    pdvSoftware: [
      { name: 'C#' },
      { name: '.Net Framework' },
      { name: 'WindowsForms' },
      { name: 'SQLite' },
      { name: 'EntityFrameworkCore' },
      { name: 'MercadoPagoSDK' },
      { name: 'Newtonsoft' }
    ],
    botDiscord: [
      { name: 'C#' },
      { name: '.NetCore' },
      { name: 'MySQL' },
      { name: 'DSharpPlus' },
      { name: 'Newtonsoft' }
    ]
  })
}
</script>

<style scoped>
@import "tailwindcss";

.experiencia {
  font-family: 'Playfair Display', serif;
}

/* Breakpoints personalizados para garantir responsividade */
@media (max-width: 480px) {
  .experiencia {
    font-size: 28px;
  }
}

@media (min-width: 481px) and (max-width: 768px) {
  .experiencia {
    font-size: 32px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .experiencia {
    font-size: 40px;
  }
}

@media (min-width: 1025px) {
  .experiencia {
    font-size: 48px;
  }
}
</style>