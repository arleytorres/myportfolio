<template>
  <section id="hero">
    <div class="h-120 bg-[#0B1324] relative overflow-hidden">
      <div class="w-full h-120 z-2 bg-black/10 backdrop-blur-sm absolute"/>

      <div class="absolute left-0 top-[30px]">
        <div class="bolinha w-50 h-50 rounded-full bg-radial from-[#0E3D44] to-[#0B1324] backdrop-blur-2xl"/>
      </div>
      <div class="absolute right-[-40px] top-[300px]">
        <div class="bolinha w-50 h-50 rounded-full bg-radial from-[#0E3D44] to-[#0B1324] backdrop-blur-2xl"/>
      </div>

      <div class="container mx-auto px-17 relative z-10 pt-16">
        <div class="grid md:grid-cols-2 mt-35">
          <div class="z-50 font-sans flex flex-col">
            <p class="text-gray-300 text-sm">Olá, eu sou</p>
            <h1 class="nome font-bold text-white mt-4 mb-4">Arley Torres</h1>
            <typewriter-text :words="frases" class="text-lg text-gray-300 font-sans mb-4"/>
            <div>
              <custom-button text="Ver Projetos" size="medium" type="primary" @click="ScrollTo('#project')" class="cursor-pointer"/>
              <custom-button text="Contato" size="small" type="secondary" @click="ScrollTo('#contact')" class="ml-2 cursor-pointer"/>
            </div>
          </div>
          <div>
            <GlowImage />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

import TypewriterText from "@/ui/TypewriterText.vue";
import CustomButton from "@/ui/CustomButton.vue";
import GlowImage from "@/ui/GlowImage.vue";

export default {
  name: "Hero",
  data:() => ({
    frases:[
        "Desenvolvedor Back-end",
        "Programação em .Net",
        "O Melhor Desenvolvimento Somente Aqui"
    ]
  }),
  components:{
    GlowImage,
    CustomButton,
    TypewriterText
  },
  methods: {
    ScrollTo(id) {
      const element = document.querySelector(id);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style scoped>
  @import "tailwindcss";
  .bolinha{
    box-shadow: 5px 5px 200px #0E3D44;
  }
  .nome{
    font-family: 'Playfair Display', serif;
    font-size: 60px;
  }
</style>