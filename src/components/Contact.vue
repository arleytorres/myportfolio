<template>
  <section id="contact" class="w-full h-150 bg-[#080C17] justify-center items-center">
    <div class="container mx-auto px-17 relative">
      <main class="grid md:grid-cols-2 gap-8">
        <div class="mt-25">
          <h2 class="contato font-bold text-white">Contato</h2>
          <p class="text-gray-400 -mt-3">Vamos conversar sobre seu projeto ou oportunidade.</p>
          <p class="mt-4 mb-2 text-white">Localização: Garanhuns, PE</p>
          <div class="flex flex-row mb-2">
            <a href="https://www.linkedin.com/in/arleytorres/" target="_blank">
              <img src="@/assets/icons/linkedin.png" alt="Linkedin" class="scale-100 cursor-pointer hover:scale-110 duration-200"/>
            </a>
            <a href="https://github.com/arleytorres" target="_blank">
              <img src="@/assets/icons/icons8-github-48.png" alt="github" class="scale-65 cursor-pointer hover:scale-75 duration-200"/>
            </a>
            <a href="mailto:arley_emanuel@hotmail.com" target="_blank">
              <img src="@/assets/icons/icons8-nova-mensagem-48.png" alt="email" class="scale-90 cursor-pointer hover:scale-100 duration-200"/>
            </a>
          </div>
        </div>
        <div>
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
.contato{
  font-family: 'Playfair Display', serif;
  font-size: 36px;

}
</style>