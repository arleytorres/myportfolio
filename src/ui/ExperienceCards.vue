<template>
  <div class="bg-[#0A101F] rounded-2xl p-6 border border-slate-700 mt-6 shadow-2xl shadow-cyan-900/20 transition-all duration-300 hover:transform hover:scale-[1.02] hover:shadow-lg hover:shadow-cyan-900">
    <p class="titulo text-white font-bold">{{titulo}}</p>
    <p class="text-gray-400 text-sm mb-2">{{data}}</p>
    <p class="text-gray-400 text-sm mb-3">{{descricao}}</p>
    <div class="flex flex-wrap gap-2">
      <span
          v-for="tecnologia in tecnologias"
          :key="tecnologia.name"
          class="px-3 py-1 text-sm rounded-full bg-gray-800 text-gray-300"
      >
        {{ tecnologia.name }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExperienceCards',
  props:{
    titulo: {
      type: String,
      required: true
    },
    descricao: {
      type: String,
      required: true
    },
    data: {
      type: String,
      required: true
    },
    tecnologias: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
@import "tailwindcss";
.titulo{
  font-size: 16px;
}
</style>