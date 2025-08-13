<template>
  <section id="hero">
    <div class="min-h-[70vh] sm:min-h-[75vh] lg:min-h-[60vh] bg-[#0B1324] relative overflow-hidden flex items-center pt-24 pb-8">
      <div class="w-full h-full z-2 bg-black/10 backdrop-blur-sm absolute"/>

      <!-- Decorative Elements -->
      <div class="absolute left-0 top-28 sm:top-32 md:top-36 lg:top-40">
        <div class="bolinha w-24 h-24 sm:w-32 sm:h-32 md:w-40 md:h-40 lg:w-48 lg:h-48 rounded-full bg-radial from-[#0E3D44] to-[#0B1324] backdrop-blur-2xl"/>
      </div>
      <div class="absolute right-[-15px] sm:right-[-20px] md:right-[-30px] bottom-20 sm:bottom-16 md:bottom-12 lg:bottom-8">
        <div class="bolinha w-24 h-24 sm:w-32 sm:h-32 md:w-40 md:h-40 lg:w-48 lg:h-48 rounded-full bg-radial from-[#0E3D44] to-[#0B1324] backdrop-blur-2xl"/>
      </div>

      <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-10 w-full">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12 items-center">

          <!-- Content Section -->
          <div class="z-50 font-sans flex flex-col text-center lg:text-left order-2 lg:order-1 w-full">
            <p class="text-gray-300 text-xs sm:text-sm mb-2 mt-5">Olá, eu sou</p>
            <h1 class="nome font-bold text-white mb-3 sm:mb-4">Arley Torres</h1>
            <div class="mb-4 sm:mb-6 min-h-[1.2rem] sm:min-h-[1.5rem]">
              <typewriter-text
                  :words="frases"
                  class="text-xs sm:text-sm md:text-base lg:text-lg text-gray-300 font-sans"
              />
            </div>

            <!-- Buttons -->
            <div class="flex flex-col sm:flex-row gap-2 sm:gap-3 justify-center lg:justify-start">
              <custom-button
                  text="Ver Projetos"
                  size="medium"
                  type="primary"
                  @click="ScrollTo('#project')"
                  class="cursor-pointer w-full sm:w-auto text-xs sm:text-sm"
              />
              <custom-button
                  text="Contato"
                  size="small"
                  type="secondary"
                  @click="ScrollTo('#contact')"
                  class="cursor-pointer w-full sm:w-auto text-xs sm:text-sm"
              />
            </div>
          </div>

          <!-- Image Section -->
          <div class="flex justify-center lg:justify-end order-1 lg:order-2">
            <div class="w-48 h-48 mt-5 sm:w-56 sm:h-56 md:w-64 md:h-64 lg:w-72 lg:h-72">
              <GlowImage />
            </div>
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
  font-size: clamp(2.5rem, 8vw, 4rem);
  line-height: 1.1;
}

@media (max-width: 640px) {
  .nome {
    font-size: 2.5rem;
  }
}

@media (min-width: 641px) and (max-width: 768px) {
  .nome {
    font-size: 3rem;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .nome {
    font-size: 3.5rem;
  }
}

@media (min-width: 1025px) {
  .nome {
    font-size: 4rem;
  }
}
</style>