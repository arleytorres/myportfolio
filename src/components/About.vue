<template>
  <section id="about" class="bg-[#080C17] h-120 w-full items-center justify-center">
    <div class="container mx-auto px-17 relative">
      <main class="grid md:grid-cols-2 gap-x-20">
        <div class="mt-20 space-y-4 w-200">
          <h2 class="sobre text-white">Sobre</h2>
          <p class="text-gray-300 text-[16px]">Sou desenvolvedor .NET com anos de experiência prática na criação de sistemas
            automações e soluções desktop e web utilizando C# e o ecossistema .NET.<br>
          </p>
          <p class="text-gray-300 text-[16px]">
            Ao longo da minha trajetória, atuei aplicando amplamente os princípios SOLID, LINQ e bancos de dados relacionais como SQL Server,
            SQLite e MySQL, sempre buscando soluções eficientes, bem estruturadas e com foco em escalabilidade.</p>
          <custom-button text="Download CV" size="small" type="primary" @click="curriculo" class="cursor-pointer"/>
        </div>
        <div class="mt-20 ml-auto mr-30">
          <div class="text-white space-y-2">
            <p>Localização: Garanhuns, PE</p>
            <p>Dispobilidade: Remoto ou Híbrido</p>
            <p>Idiomas: Português (nativo), Inglês (intermediario)</p>
          </div>
        </div>
      </main>
    </div>
  </section>
</template>

<script>
import customButton from "@/ui/CustomButton.vue";
export default {
  name: 'About'
  ,components: {
    customButton
  },
  data:() => ({
  }),
  methods: {
    curriculo() {
      const link = document.createElement('a');
      link.href = '/src/assets/documents/Curriculo.pdf';
      link.download = 'CV_Arley_Torres.pdf';
      link.click();
    }
  }
}
</script>

<style scoped>
@import "tailwindcss";
.sobre{
  font-family: playfair-display, serif;
  font-size: 36px;
}
</style>