<template>
  <section id="skills" class="h-210 bg-[#080C17] w-full items-center justify-center text-white">
    <div class="container mx-auto px-17 relative">
      <main class="grid md:grid-cols-2 gap-8">
        <div>
          <h2 class="skills text-white mb-6">Skills</h2>
          <SkillsCard
            title="Backend"
            :skills="backendSkills"
            imagem="icons8-servidores-50.png"
            progress-bar-color="bg-sky-500">
          </SkillsCard>
          <SkillsCard
              title="Frontend"
              :skills="frontendSkills"
              imagem="icons8-code-50.png"
              progress-bar-color="bg-red-500"
              class="mt-4">
          </SkillsCard>
        </div>
        <div>
          <SkillsCard
              title="Banco de Dados"
              :skills="dataBaseSkills"
              imagem="icons8-database-50.png"
              progress-bar-color="bg-emerald-500"
              class="mt-19">
          </SkillsCard>
          <SkillsCard
              title="Outros"
              :skills="outraSkills"
              imagem="icons8-conexão-desligada-50.png"
              progress-bar-color="bg-yellow-500"
              class="mt-4">
          </SkillsCard>
        </div>
      </main>
    </div>
  </section>
</template>

<script>
import SkillsCard from "@/ui/SkillsCard.vue";
export default {
  name: 'Skills',
  components:{
    SkillsCard
  },
  data:() => ({
    backendSkills: [
      { name: '.Net 9.0', percentage: 70 },
      { name: '.Net Framework', percentage: 85 },
      { name: 'PHP', percentage: 30 },
      {name: 'Lua', percentage: 40 }
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
  font-size: 36px;
}
</style>