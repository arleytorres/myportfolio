<template>
  <Header />
  <Hero />
  <About />
  <Skills />
  <Experience />
  <Projects />
  <Contact />
  <Footer />
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from "@/components/About.vue";
import Skills from "@/components/Skills.vue";
import Experience from "@/components/Experience.vue";
import Projects from "@/components/Projects.vue";
import Contact from "@/components/Contact.vue";
import Footer from "@/components/Footer.vue";

export default{
  name: 'App',
  components:{
    Header,
    Hero,
    About,
    Skills,
    Experience,
    Projects,
    Contact,
    Footer
  }
}

</script>

<style>
  @import "tailwindcss";
  html{
    scroll-behavior: smooth;
  }
</style>