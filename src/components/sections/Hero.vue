<script setup>
function scrollTo(id) {
  const el = document.getElementById(id)
  if (!el) return
  const top = el.getBoundingClientRect().top + window.scrollY - 100
  window.scrollTo({ top, behavior: 'smooth' })
}
</script>

<template>
  <section
    class="relative flex h-screen flex-col justify-center px-6 pt-20"
    style="background: linear-gradient(to bottom right, rgba(10, 25, 47, 0.9), rgba(10, 25, 47, 1))"
  >
    <div class="container mx-auto max-w-5xl">
      <div class="animate-fadeIn opacity-0" style="animation-delay: 0.2s">
        <p class="mb-5 font-mono text-highlight">Hi, my name is</p>
      </div>
      <div class="animate-fadeIn opacity-0" style="animation-delay: 0.4s">
        <h1 class="mb-4 text-4xl font-bold text-slate-lightest sm:text-5xl md:text-6xl lg:text-7xl">
          Roshif Srivastava
        </h1>
      </div>
      <div class="animate-fadeIn opacity-0" style="animation-delay: 0.6s">
        <h2 class="mb-8 text-3xl font-bold text-slate sm:text-4xl md:text-5xl lg:text-6xl">
          I build exceptional web experiences.
        </h2>
      </div>
      <div class="animate-fadeIn opacity-0" style="animation-delay: 0.8s">
        <p class="mb-10 max-w-2xl text-lg text-slate-light">
          I'm a Principal Engineer and Front-End Developer with 13+ years of experience
          specializing in building high-quality, responsive, and user-focused web applications.
          Currently leading development at <span class="text-highlight">Caastle.com</span>.
        </p>
      </div>
      <div class="animate-fadeIn opacity-0" style="animation-delay: 1s">
        <button
          type="button"
          class="inline-block cursor-pointer rounded border border-highlight px-8 py-4 font-mono text-highlight transition-all duration-300 hover:bg-highlight/10"
          @click="scrollTo('projects')"
        >
          Check out my work
        </button>
      </div>
    </div>

    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-fadeIn opacity-0" style="animation-delay: 1.2s">
      <button
        type="button"
        class="flex cursor-pointer flex-col items-center text-slate-light transition-colors duration-300 hover:text-highlight"
        @click="scrollTo('about')"
      >
        <span class="mb-2 text-sm">Scroll Down</span>
        <svg class="animate-bounce" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <circle cx="12" cy="12" r="10" /><path d="M12 8v8" /><path d="m8 12 4 4 4-4" />
        </svg>
      </button>
    </div>
  </section>
</template>
