<template>
  <section id="skills" class="py-12 sm:py-16 lg:py-20 bg-[#080C17] w-full">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="mb-8 sm:mb-12">
        <h2 class="skills text-white text-2xl sm:text-3xl lg:text-4xl lg:text-left">
          Skills
        </h2>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 lg:gap-8">
        <!-- Primeira Coluna -->
        <div class="space-y-6">
          <SkillsCard
              title="Backend"
              :skills="backendSkills"
              imagem="icons8-servidores-50.png"
              progress-bar-color="bg-sky-500"
          />
          <SkillsCard
              title="Frontend"
              :skills="frontendSkills"
              imagem="icons8-code-50.png"
              progress-bar-color="bg-red-500"
          />
        </div>

        <!-- Segunda Coluna -->
        <div class="space-y-6">
          <SkillsCard
              title="Banco de Dados"
              :skills="dataBaseSkills"
              imagem="icons8-database-50.png"
              progress-bar-color="bg-emerald-500"
          />
          <SkillsCard
              title="Outros"
              :skills="outraSkills"
              imagem="icons8-conexão-desligada-50.png"
              progress-bar-color="bg-yellow-500"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import SkillsCard from "@/ui/SkillsCard.vue";

export default {
  name: 'Skills',
  components: {
    SkillsCard
  },
  data: () => ({
    backendSkills: [
      { name: '.Net 9.0', percentage: 70 },
      { name: '.Net Framework', percentage: 85 },
      { name: 'PHP', percentage: 30 },
      { name: 'Lua', percentage: 40 }
    ],
    dataBaseSkills: [
      { name: 'SQL Server', percentage: 70 },
      { name: 'Oracle', percentage: 30 },
      { name: 'MySQL', percentage: 80 },
      { name: 'MongoDB', percentage: 65 }
    ],
    frontendSkills: [
      { name: 'Angular', percentage: 40 },
      { name: 'JavaScript', percentage: 60 },
      { name: 'Typescript', percentage: 50 }
    ],
    outraSkills: [
      { name: 'Kafka', percentage: 40 },
      { name: 'EntityFrameworkCore', percentage: 50 },
      { name: 'MVC', percentage: 60 }
    ]
  })
}
</script>

<style scoped>
@import "tailwindcss";

.skills {
  font-family: 'Playfair Display', serif;
  line-height: 1.2;
}

/* Mobile */
@media (max-width: 640px) {
  .skills {
    font-size: 1.5rem;
  }
}

/* Tablet */
@media (min-width: 641px) and (max-width: 1023px) {
  .skills {
    font-size: 1.875rem;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .skills {
    font-size: 2.25rem;
  }
}
</style>