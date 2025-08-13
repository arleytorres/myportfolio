<template>
  <section>
    <footer class="w-full border-t border-gray-700 h-auto min-h-[6rem] bg-[#080C17] flex justify-center items-center py-4 sm:py-6">
      <div class="container mx-auto px-4 sm:px-6 md:px-8 lg:px-12 xl:px-16 max-w-7xl">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 md:gap-8 text-center md:text-left">
          <!-- Copyright -->
          <p class="text-xs sm:text-sm text-gray-400 order-2 md:order-1">
            © 2025 Arley Torres. Todos os direitos reservados.
          </p>

          <!-- Localização -->
          <p class="text-xs sm:text-sm text-gray-400 order-1 md:order-2 md:text-right">
            Pernambuco, BR
          </p>
        </div>
      </div>
    </footer>
  </section>
</template>

<script>
export default {
  name: 'Footer',
  data: () => ({
  })
}
</script>

<style scoped>
/* Garantir que o footer seja sempre visível */
@media (max-width: 768px) {
  footer {
    min-height: 5rem;
  }
}

@media (min-width: 769px) {
  footer {
    min-height: 6rem;
  }
}
</style>