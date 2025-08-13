<template>
  <div class="bg-[#0A101F] rounded-2xl p-6 border border-slate-700 shadow-2xl shadow-cyan-900/20 transition-all duration-300 hover:transform hover:scale-[1.02] hover:shadow-lg hover:shadow-cyan-900">
    <div class="w-full mb-6">
      <img
          :src="'/public/images/' + imagem"
          :alt="titulo"
          class="w-full h-[300px] object-cover rounded-2xl"
      />
    </div>
    <div class="w-full">
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
      <div v-if="buttom" class="flex mt-6 mb-2 ml-4">
        <CustomButton text="Ver Codigo"
                      size="medium"
                      type="primary"
                      @click="Link" />

      </div>
    </div>
  </div>
</template>

<script>
import CustomButton from "@/ui/CustomButton.vue";
export default {
  name: 'ProjectsCards',
  data: () => ({}),
  props: {
    titulo: String,
    descricao: String,
    data: String,
    tecnologias: Array,
    imagem: {
      type: String,
      default: "/assets/images/imagem_padrão.png"
    },
    buttom: {
      type: Boolean,
      default: false
    },
    linkPassado: {
      type: String
    }
  },
    components: {
      CustomButton
    },
    methods: {
      Link() {
        const link = document.createElement('a');
        link.href = this.linkPassado;
        link.target = '_blank';
        link.click();
      }
    }

}
</script>

<style scoped>
.titulo {
  font-size: 18px;
}
</style>