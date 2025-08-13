<template>
  <section id="about" class="bg-[#080C17] py-12 sm:py-16 lg:py-20 w-full">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-16">

        <!-- Content Section -->
        <div class="space-y-4 sm:space-y-6">
          <h2 class="sobre text-white text-2xl sm:text-3xl lg:text-4xl mb-4 sm:mb-6">Sobre</h2>

          <div class="space-y-4">
            <p class="text-gray-300 text-sm sm:text-base leading-relaxed">
              Sou desenvolvedor .NET com anos de experiência prática na criação de sistemas, automações e soluções desktop e web utilizando C# e o ecossistema .NET.
            </p>

            <p class="text-gray-300 text-sm sm:text-base leading-relaxed">
              Ao longo da minha trajetória, atuei aplicando amplamente os princípios SOLID, LINQ e bancos de dados relacionais como SQL Server, SQLite e MySQL, sempre buscando soluções eficientes, bem estruturadas e com foco em escalabilidade.
            </p>
          </div>

          <div class="pt-4">
            <custom-button
                text="Download CV"
                size="small"
                type="primary"
                @click="curriculo"
                class="cursor-pointer w-full sm:w-auto"
            />
          </div>
        </div>

        <!-- Info Section -->
        <div class="space-y-3 sm:space-y-4 lg:mt-16">
          <div class="text-white space-y-2 sm:space-y-3 text-sm sm:text-base">
            <div class="flex flex-col sm:flex-row sm:items-center">
              <span class="font-medium text-gray-400 min-w-[120px]">Localização:</span>
              <span class="text-white">Garanhuns, PE</span>
            </div>

            <div class="flex flex-col sm:flex-row sm:items-center">
              <span class="font-medium text-gray-400 min-w-[120px]">Disponibilidade:</span>
              <span class="text-white">Remoto ou Híbrido</span>
            </div>

            <div class="flex flex-col sm:flex-row sm:items-start">
              <span class="font-medium text-gray-400 min-w-[120px]">Idiomas:</span>
              <span class="text-white">Português (nativo)<br class="sm:hidden">Inglês (intermediário)</span>
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
    },
    curriculo() {
      const link = document.createElement('a');
      link.href = '/documents/Curriculo.pdf';
      link.download = 'CV_Arley_Torres.pdf';
      link.click();
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
  font-size: clamp(1.8rem, 6vw, 3.5rem);
  line-height: 1.1;
}

.sobre{
  font-family: 'Playfair Display', serif;
  line-height: 1.2;
}

/* Mobile optimizations */
@media (max-width: 640px) {
  .nome {
    font-size: 1.6rem;
  }
  .sobre {
    font-size: 1.5rem;
  }
}

/* Tablet */
@media (min-width: 641px) and (max-width: 768px) {
  .nome {
    font-size: 2.2rem;
  }
  .sobre {
    font-size: 1.8rem;
  }
}

/* Desktop */
@media (min-width: 769px) {
  .nome {
    font-size: 2.8rem;
  }
  .sobre {
    font-size: 2.25rem;
  }
}

@media (min-width: 1024px) {
  .nome {
    font-size: 3.5rem;
  }
  .sobre {
    font-size: 2.5rem;
  }
}
</style>