<template>
  <header class="fixed top-0 w-full z-50 h-16 bg-gray-900/30 backdrop-blur-sm border-b border-gray-700">
    <div class="container mx-auto px-4 h-full">
      <div class="flex items-center justify-between h-full text-gray-300 text-sm">

        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="#hero">
            <p class="font-bold hover:scale-110 transition-transform text-white text-base cursor-pointer">
              Arley_Torres
            </p>
          </a>
        </div>

        <!-- Desktop Menu -->
        <nav class="hidden lg:flex items-center justify-center flex-1 mx-8">
          <div class="flex space-x-6">
            <a href="#hero" class="hover:text-white cursor-pointer transition-colors">Início</a>
            <a href="#about" class="hover:text-white cursor-pointer transition-colors">Sobre</a>
            <a href="#skills" class="hover:text-white cursor-pointer transition-colors">Skills</a>
            <a href="#experience" class="hover:text-white cursor-pointer transition-colors">Experiência</a>
            <a href="#project" class="hover:text-white cursor-pointer transition-colors">Projetos</a>
            <a href="#contact" class="hover:text-white cursor-pointer transition-colors">Contato</a>
          </div>
        </nav>

        <!-- Desktop CTA -->
        <div class="hidden lg:block flex-shrink-0">
          <a href="#project">
            <p class="hover:text-white hover:underline cursor-pointer transition-colors">
              Ver Projetos
            </p>
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <button
            @click="mobileMenuOpen = !mobileMenuOpen"
            class="lg:hidden p-2 text-gray-300 hover:text-white transition-colors focus:outline-none"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
                v-if="!mobileMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
            />
            <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div
          v-if="mobileMenuOpen"
          class="lg:hidden absolute top-16 left-0 right-0 bg-gray-900/95 backdrop-blur-sm border-b border-gray-700"
      >
        <nav class="px-4 py-4 space-y-3">
          <a
              href="#hero"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Início
          </a>
          <a
              href="#about"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Sobre
          </a>
          <a
              href="#skills"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Skills
          </a>
          <a
              href="#experience"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Experiência
          </a>
          <a
              href="#project"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Projetos
          </a>
          <a
              href="#contact"
              @click="mobileMenuOpen = false"
              class="block py-2 text-gray-300 hover:text-white transition-colors"
          >
            Contato
          </a>
          <div class="pt-3 border-t border-gray-700">
            <a
                href="#project"
                @click="mobileMenuOpen = false"
                class="block py-2 text-white font-medium hover:underline transition-colors"
            >
              Ver Projetos
            </a>
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      mobileMenuOpen: false
    }
  },
  mounted() {
    // Fecha menu mobile ao clicar fora
    document.addEventListener('click', (e) => {
      if (!this.$el.contains(e.target)) {
        this.mobileMenuOpen = false
      }
    })
  }
}
</script>