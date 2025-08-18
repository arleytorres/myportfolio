<template>
  <section id="contact" class="w-full min-h-screen bg-[#080C17] flex justify-center items-center py-8 sm:py-12 md:py-16 lg:py-20">
    <div class="container mx-auto px-4 sm:px-6 md:px-8 lg:px-12 xl:px-16 relative max-w-7xl">
      <main class="grid grid-cols-1 lg:grid-cols-2 gap-8 sm:gap-10 md:gap-12 lg:gap-16 xl:gap-20 w-full">
        <div class="order-2 lg:order-1 text-center lg:text-left">
          <h2 class="contato font-bold text-white text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl mb-3 sm:mb-4 md:mb-6">
            Contato
          </h2>
          <p class="text-gray-400 text-sm sm:text-base md:text-lg lg:text-xl mb-4 sm:mb-6 md:mb-8">
            Vamos conversar sobre seu projeto ou oportunidade.
          </p>
          <p class="text-white text-sm sm:text-base md:text-lg mb-4 sm:mb-6">
            Localização: Garanhuns, PE
          </p>
          <div class="flex flex-row justify-center lg:justify-start items-center gap-2 sm:gap-3 md:gap-4">
            <a href="https://www.linkedin.com/in/arleytorres/" target="_blank" class="transition-transform hover:scale-110 duration-200">
              <img
                  src="/icons/linkedin.png"
                  alt="Linkedin"
                  class="w-8 h-8 sm:w-10 sm:h-10 md:w-12 md:h-12 cursor-pointer scale-130"
              />
            </a>
            <a href="https://github.com/arleytorres" target="_blank" class="transition-transform hover:scale-110 duration-200">
              <img
                  src="/icons/icons8-github-48.png"
                  alt="github"
                  class="w-8 h-8 sm:w-10 sm:h-10 md:w-12 md:h-12 cursor-pointer"
              />
            </a>
            <a href="mailto:contato@torresdev.online" target="_blank" class="transition-transform hover:scale-110 duration-200">
              <img
                  src="/icons/icons8-nova-mensagem-48.png"
                  alt="email"
                  class="w-8 h-8 sm:w-10 sm:h-10 md:w-12 md:h-12 cursor-pointer scale-110"
              />
            </a>
          </div>
        </div>
        <div class="order-1 lg:order-2 w-full">
          <ContactCardEmail />
        </div>
      </main>
    </div>
  </section>
</template>

<script>
import ContactCardEmail from "@/ui/ContactCardEmail.vue";

export default {
  name: 'Contact',
  components: {
    ContactCardEmail
  }
}
</script>

<style scoped>
.contato {
  font-family: 'Playfair Display', serif;
}

@media (max-width: 480px) {
  .contato {
    font-size: 28px;
  }
}

@media (min-width: 481px) and (max-width: 768px) {
  .contato {
    font-size: 32px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .contato {
    font-size: 40px;
  }
}

@media (min-width: 1025px) {
  .contato {
    font-size: 48px;
  }
}
</style>
