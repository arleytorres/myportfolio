<template>
  <div class="bg-[#0A101F] rounded-2xl p-6 border border-slate-700">
    <div class="flex items-center gap-1 mb-6">
      <div class="w-6 h-6 overflow-hidden">
        <img
            :src="'/src/assets/icons/' + imagem"
            :alt="icones"
            class="w-full h-full object-contain"
        />
      </div>
      <h2 class="text-white text-lg">{{ title }}</h2>
    </div>
    <div class="space-y-4">
      <div v-for="skill in skills" :key="skill.name" class="space-y-2">
        <div class="flex justify-between text-sm">
          <span class="nomeSkill text-gray-300">{{ skill.name }}</span>
          <span class="text-gray-400">{{ skill.percentage }}%</span>
        </div>
        <div class="w-full h-4 bg-slate-700 rounded-full">
          <div
              class="h-4 rounded-full"
              :class="progressBarColor"
              :style="`width: ${skill.percentage}%`"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SkillCard',
  props: {
    title: {
      type: String,
      required: true
    },
    skills: {
      type: Array,
      required: true
    },
    progressBarColor: {
      type: String,
      default: 'bg-cyan-500'
    },
    imagem: {
      type: String,
      required: true
    }
  }
}
</script>
<style scoped>
@import "tailwindcss";
.nomeSkill{
  font-family: sans-serif;
}
</style>