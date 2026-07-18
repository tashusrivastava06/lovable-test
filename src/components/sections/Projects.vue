<script setup>
import { computed } from 'vue'

const projects = [
  {
    title: 'Storefront Builder',
    description: 'A templated, configurable system for rapid onboarding of D2C brands that automates CSS/text variable integration via scripts. Built with React and SASS for scalable, efficient client setups.',
    technologies: ['React', 'SASS', 'JavaScript', 'API Integration'],
    featured: true,
  },
  {
    title: 'Brand Asset Collection Tool',
    description: 'A React-based tool with real-time preview capabilities, enabling quick onboarding of brand assets with dynamic website updates. Streamlines the collection process and ensures visual consistency.',
    technologies: ['React', 'Redux', 'RESTful APIs', 'Real-time Preview'],
    featured: true,
  },
  {
    title: 'D2C Subscription Model',
    description: 'Led React-based frontend development for onboarding brands like Vince, Rebecca Taylor, and Express into subscription models. Implemented responsive designs with seamless API integrations.',
    technologies: ['React', 'TailwindCSS', 'API Integration', 'Responsive Design'],
    featured: true,
  },
  {
    title: 'REACH Payment Platform',
    description: 'Developed mobile & desktop web platform for accepting online payments through all modes – Debit Card, Credit Card & Net Banking. Built responsive front-end with AngularJS and REST API integration.',
    technologies: ['AngularJS', 'HTML5', 'CSS3', 'LESS', 'REST APIs'],
  },
  {
    title: 'Clothing Rental Web Apps',
    description: 'Built websites for Gwynniebee & Haverdash using React and BEM methodology, supporting expansion from plus-size to inclusive sizing with responsive design principles.',
    technologies: ['React', 'BEM', 'CSS3', 'JavaScript', 'Responsive Design'],
  },
  {
    title: 'Email Marketing System',
    description: 'Independently developed dynamic, personalized emails using AMPscript and Data Extensions in Salesforce Marketing Cloud (SFMC), enhancing customer engagement through tailored communications.',
    technologies: ['SFMC', 'AMPscript', 'Data Extensions', 'HTML/CSS'],
  },
]

const featuredProjects = computed(() => projects.filter((p) => p.featured))
const otherProjects = computed(() => projects.filter((p) => !p.featured))
</script>

<template>
  <section id="projects" class="bg-navy-light px-6 py-20">
    <div class="container mx-auto max-w-5xl">
      <h2 class="section-heading">
        <span class="number">04.</span> Things I've Built
      </h2>

      <!-- Featured Projects -->
      <div class="mb-24 space-y-32">
        <div
          v-for="(project, i) in featuredProjects"
          :key="project.title"
          class="relative grid grid-cols-12 items-center animate-slideUp opacity-0"
          :style="{ animationDelay: `${0.2 + i * 0.2}s` }"
        >
          <!-- Project Image (placeholder) -->
          <div
            class="relative row-start-1 col-span-full lg:col-span-7"
            :class="i % 2 === 0 ? 'lg:col-start-1' : 'lg:col-start-6'"
          >
            <div class="relative aspect-video overflow-hidden rounded border border-slate/20 bg-navy-dark">
              <div class="absolute inset-0 flex items-center justify-center text-slate-light">
                {{ project.title }} Screenshot
              </div>
            </div>
          </div>

          <!-- Project Content -->
          <div
            class="relative z-10 row-start-1 col-span-full p-6 lg:col-span-6 lg:p-0"
            :class="i % 2 === 0 ? 'lg:col-start-7 lg:text-right' : 'lg:col-start-1 lg:text-left'"
            style="background-color: rgba(17, 34, 64, 0.85); backdrop-filter: blur(4px); -webkit-backdrop-filter: blur(4px)"
          >
            <div class="lg:p-8">
              <p class="mb-2 font-mono text-sm text-highlight">Featured Project</p>
              <h3 class="mb-4 text-2xl font-semibold text-slate-lightest">{{ project.title }}</h3>
              <div class="mb-4 rounded bg-navy-dark p-6">
                <p class="text-slate-light">{{ project.description }}</p>
              </div>
              <ul class="mb-6 flex flex-wrap gap-2" :class="i % 2 === 0 ? 'lg:justify-end' : 'lg:justify-start'">
                <li v-for="tech in project.technologies" :key="tech" class="font-mono text-xs text-slate-light">
                  {{ tech }}
                </li>
              </ul>
              <div class="flex gap-4" :class="i % 2 === 0 ? 'lg:justify-end' : 'lg:justify-start'">
                <a
                  v-if="project.githubLink"
                  :href="project.githubLink"
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="GitHub Repository"
                >
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-slate-lighter hover:text-highlight">
                    <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 1.5 5 1.5 5 1.5c-.3 1.15-.3 2.35 0 3.5A5.4 5.4 0 0 0 4 8.5c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4" />
                    <path d="M9 18c-4.51 2-5-2-7-2" />
                  </svg>
                </a>
                <a
                  v-if="project.externalLink"
                  :href="project.externalLink"
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="Live Project"
                >
                  <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-slate-lighter hover:text-highlight">
                    <path d="M15 3h6v6" /><path d="M10 14 21 3" /><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6" />
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Other Projects -->
      <h3 class="mb-8 text-center text-2xl font-semibold text-slate-lightest">
        Other Noteworthy Projects
      </h3>

      <div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
        <div
          v-for="(project, i) in otherProjects"
          :key="project.title"
          class="h-full rounded-lg border border-slate/20 bg-navy-dark transition-all duration-300 animate-slideUp opacity-0 hover:border-highlight"
          :style="{ animationDelay: `${0.4 + i * 0.2}s` }"
        >
          <div class="flex h-full flex-col p-6">
            <div class="mb-6 flex items-start justify-between">
              <div class="text-highlight">
                <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z" />
                </svg>
              </div>
              <div class="flex gap-3">
                <a
                  v-if="project.githubLink"
                  :href="project.githubLink"
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="GitHub Repository"
                >
                  <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-slate-lighter hover:text-highlight">
                    <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 1.5 5 1.5 5 1.5c-.3 1.15-.3 2.35 0 3.5A5.4 5.4 0 0 0 4 8.5c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4" />
                    <path d="M9 18c-4.51 2-5-2-7-2" />
                  </svg>
                </a>
                <a
                  v-if="project.externalLink"
                  :href="project.externalLink"
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="Live Project"
                >
                  <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-slate-lighter hover:text-highlight">
                    <path d="M15 3h6v6" /><path d="M10 14 21 3" /><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6" />
                  </svg>
                </a>
              </div>
            </div>
            <h3 class="mb-3 text-xl font-semibold text-slate-lightest">{{ project.title }}</h3>
            <p class="mb-6 grow text-slate-light">{{ project.description }}</p>
            <div class="mt-auto flex flex-wrap gap-2">
              <span
                v-for="tech in project.technologies"
                :key="tech"
                class="inline-flex items-center rounded-full border border-slate/30 px-2.5 py-0.5 font-mono text-xs text-slate-light"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
