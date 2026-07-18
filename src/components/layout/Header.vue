<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isMenuOpen = ref(false)
const isScrolled = ref(false)

const menuItems = [
  { name: 'About', to: 'about' },
  { name: 'Experience', to: 'experience' },
  { name: 'Skills', to: 'skills' },
  { name: 'Projects', to: 'projects' },
  { name: 'Contact', to: 'contact' },
]

function handleScroll() {
  isScrolled.value = window.scrollY > 20
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))

function scrollToSection(id) {
  const el = document.getElementById(id)
  if (!el) return
  const top = el.getBoundingClientRect().top + window.scrollY - 100
  window.scrollTo({ top, behavior: 'smooth' })
  isMenuOpen.value = false
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <header
    class="fixed z-50 flex w-full items-center justify-between px-6 transition-all duration-300"
    :class="isScrolled ? 'bg-navy/90 py-4 shadow-md backdrop-blur' : 'py-6'"
  >
    <div class="flex items-center">
      <button type="button" class="font-mono text-2xl font-bold text-highlight" @click="scrollToTop">AS</button>
    </div>

    <!-- Desktop Navigation -->
    <nav class="hidden md:block">
      <ul class="flex items-center space-x-8">
        <li v-for="(item, i) in menuItems" :key="item.to" class="text-sm">
          <button
            type="button"
            class="cursor-pointer py-2 font-mono text-slate-lighter transition-colors duration-300 hover:text-highlight"
            @click="scrollToSection(item.to)"
          >
            <span class="mr-1 text-highlight">{{ `0${i + 1}.` }}</span> {{ item.name }}
          </button>
        </li>
        <li>
          <a
            href="/resume.pdf"
            target="_blank"
            rel="noopener noreferrer"
            class="rounded border border-highlight px-4 py-2 font-mono text-sm text-highlight transition-all duration-300 hover:bg-highlight/10"
          >
            Resume
          </a>
        </li>
      </ul>
    </nav>

    <!-- Mobile Menu Button -->
    <button
      class="text-highlight md:hidden"
      aria-label="Toggle menu"
      @click="isMenuOpen = !isMenuOpen"
    >
      <svg v-if="!isMenuOpen" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <line x1="4" y1="12" x2="20" y2="12" /><line x1="4" y1="6" x2="20" y2="6" /><line x1="4" y1="18" x2="20" y2="18" />
      </svg>
      <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <line x1="18" y1="6" x2="6" y2="18" /><line x1="6" y1="6" x2="18" y2="18" />
      </svg>
    </button>

    <!-- Mobile Menu -->
    <div
      class="fixed top-0 right-0 z-50 h-screen w-3/4 transform bg-navy-light shadow-xl transition-transform duration-300 ease-in-out md:hidden"
      :class="isMenuOpen ? 'translate-x-0' : 'translate-x-full'"
    >
      <div class="flex justify-end p-6">
        <button aria-label="Close menu" class="text-highlight" @click="isMenuOpen = false">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <line x1="18" y1="6" x2="6" y2="18" /><line x1="6" y1="6" x2="18" y2="18" />
          </svg>
        </button>
      </div>

      <nav class="mt-16 flex flex-col items-center space-y-8">
        <button
          v-for="(item, i) in menuItems"
          :key="item.to"
          type="button"
          class="cursor-pointer font-mono text-lg text-slate-lighter transition-colors duration-300 hover:text-highlight"
          @click="scrollToSection(item.to)"
        >
          <span class="mr-1 text-highlight">{{ `0${i + 1}.` }}</span> {{ item.name }}
        </button>
        <a
          href="/resume.pdf"
          target="_blank"
          rel="noopener noreferrer"
          class="mt-4 rounded border border-highlight px-8 py-2 font-mono text-highlight transition-all duration-300 hover:bg-highlight/10"
        >
          Resume
        </a>
      </nav>
    </div>

    <!-- Overlay -->
    <div
      v-if="isMenuOpen"
      class="fixed inset-0 z-40 bg-black/50 md:hidden"
      @click="isMenuOpen = false"
    />
  </header>
</template>
