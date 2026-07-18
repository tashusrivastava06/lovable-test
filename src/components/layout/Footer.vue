<script setup>
const year = new Date().getFullYear()
</script>

<template>
  <footer class="bg-navy-dark px-6 py-6">
    <div class="container mx-auto max-w-6xl">
      <div class="flex flex-col items-center justify-between md:flex-row">
        <div class="mb-4 text-sm text-slate md:mb-0">
          © {{ year }} Abhishek Srivastava. All rights reserved.
        </div>

        <div class="flex space-x-6">
          <a
            href="https://github.com/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub Profile"
            class="text-slate transition-colors duration-300 hover:text-highlight"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 1.5 5 1.5 5 1.5c-.3 1.15-.3 2.35 0 3.5A5.4 5.4 0 0 0 4 8.5c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4" />
              <path d="M9 18c-4.51 2-5-2-7-2" />
            </svg>
          </a>
          <a
            href="https://linkedin.com/in/"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn Profile"
            class="text-slate transition-colors duration-300 hover:text-highlight"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z" />
              <rect width="4" height="12" x="2" y="9" /><circle cx="4" cy="4" r="2" />
            </svg>
          </a>
          <a
            href="mailto:tashusrivastava06@gmail.com"
            aria-label="Email"
            class="text-slate transition-colors duration-300 hover:text-highlight"
          >
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <rect width="20" height="16" x="2" y="4" rx="2" /><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7" />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>
