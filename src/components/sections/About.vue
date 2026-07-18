<script setup>
const skills = [
  'ReactJS',
  'JavaScript (ES6+)',
  'CSS3/SASS/SCSS',
  'TailwindCSS',
  'HTML5',
  'Responsive Design',
  'API Integration',
  'Salesforce Marketing Cloud',
]
</script>

<template>
  <section id="about" class="bg-navy px-6 py-20">
    <div class="container mx-auto max-w-5xl">
      <h2 class="section-heading">
        <span class="number">01.</span> About Me
      </h2>

      <div class="grid grid-cols-1 gap-10 md:grid-cols-3">
        <div class="col-span-2 animate-slideUp opacity-0" style="animation-delay: 0.2s">
          <p class="mb-4 text-lg">
            Hello! I'm Roshif, a passionate Front-End Developer with over 13 years of experience in creating dynamic,
            responsive, and user-focused web applications. My journey in web development began back in 2010,
            and I've been in love with crafting digital experiences ever since.
          </p>

          <p class="mb-4">
            As a Principal Engineer at <span class="text-highlight">Caastle.com</span> (formerly Gwynnie Bee),
            I lead development teams, implement best practices, and define scalable frontend architectures.
            I've had the privilege of working on diverse projects from subscription-based clothing rental platforms
            to innovative e-commerce solutions.
          </p>

          <p class="mb-6">
            My expertise spans modern front-end technologies including:
          </p>

          <ul class="mb-8 grid grid-cols-2 gap-x-4 gap-y-2">
            <li v-for="skill in skills" :key="skill" class="flex items-center">
              <span class="mr-2 text-highlight">▹</span> {{ skill }}
            </li>
          </ul>

          <p>
            I'm dedicated to creating efficient, maintainable code and delivering exceptional user experiences.
            Whether leading teams or diving deep into code, I focus on building solutions that are both technically
            sound and user-friendly.
          </p>
        </div>

        <div class="relative animate-slideUp opacity-0" style="animation-delay: 0.4s">
          <div class="group relative">
            <div class="absolute -inset-1 rounded bg-highlight/20 opacity-75 blur transition duration-300 group-hover:opacity-100" />
            <div class="relative h-auto max-w-full overflow-hidden rounded">
              <div class="relative h-0 w-full" style="padding-bottom: 100%">
                <div class="absolute inset-0 overflow-hidden rounded border-2 border-highlight bg-navy-light">
                  <div class="flex h-full w-full items-center justify-center font-mono text-lg text-highlight">
                    Your photo here
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="absolute top-4 left-4 -z-10 h-full w-full rounded border-2 border-highlight" />
        </div>
      </div>
    </div>
  </section>
</template>
