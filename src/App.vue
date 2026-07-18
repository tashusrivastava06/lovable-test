<script setup>
import Header from './components/layout/Header.vue'
import Footer from './components/layout/Footer.vue'
import Hero from './components/sections/Hero.vue'
import About from './components/sections/About.vue'
import Experience from './components/sections/Experience.vue'
import Skills from './components/sections/Skills.vue'
import Projects from './components/sections/Projects.vue'
import Contact from './components/sections/Contact.vue'
</script>

<template>
  <div class="flex min-h-screen flex-col">
    <Header />
    <main class="grow">
      <Hero />
      <About />
      <Experience />
      <Skills />
      <Projects />
      <Contact />
    </main>
    <Footer />
  </div>
</template>
