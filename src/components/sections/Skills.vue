<script setup>
const skillCategories = [
  {
    name: 'Front-End Technologies',
    skills: [
      { name: 'HTML5', proficiency: 95 },
      { name: 'CSS3/SASS/SCSS', proficiency: 95 },
      { name: 'JavaScript (ES6+)', proficiency: 90 },
      { name: 'ReactJS', proficiency: 90 },
      { name: 'TailwindCSS', proficiency: 85 },
      { name: 'jQuery', proficiency: 85 },
      { name: 'Responsive Design', proficiency: 95 },
    ],
  },
  {
    name: 'Tools & Platforms',
    skills: [
      { name: 'Git/GitHub/Bitbucket', proficiency: 90 },
      { name: 'Figma/Adobe Photoshop', proficiency: 80 },
      { name: 'Jira', proficiency: 85 },
      { name: 'Salesforce Marketing Cloud', proficiency: 80 },
      { name: 'Shopify', proficiency: 75 },
      { name: 'Storybook', proficiency: 85 },
    ],
  },
  {
    name: 'Development Practices',
    skills: [
      { name: 'Cross-browser Compatibility', proficiency: 95 },
      { name: 'Performance Optimization', proficiency: 90 },
      { name: 'Agile/Scrum Methodologies', proficiency: 85 },
      { name: 'Team Leadership', proficiency: 90 },
      { name: 'API Integration', proficiency: 85 },
      { name: 'SEO Best Practices', proficiency: 80 },
    ],
  },
]

const competencies = [
  'Front-End Development',
  'Responsive Design',
  'API Integration',
  'Performance Optimization',
  'Cross-Browser Compatibility',
  'Agile & Scrum',
  'Team Leadership',
  'Email Development',
  'UI/UX Collaboration',
  'Single Page Applications',
  'Mentoring',
  'Email Marketing',
]
</script>

<template>
  <section id="skills" class="bg-navy px-6 py-20">
    <div class="container mx-auto max-w-5xl">
      <h2 class="section-heading">
        <span class="number">03.</span> My Skills
      </h2>

      <div class="grid grid-cols-1 gap-12 lg:grid-cols-2">
        <div
          v-for="(category, i) in skillCategories"
          :key="category.name"
          class="animate-slideUp opacity-0"
          :style="{ animationDelay: `${0.2 + i * 0.2}s` }"
        >
          <h3 class="mb-6 font-mono text-xl text-highlight">{{ category.name }}</h3>
          <div class="space-y-5">
            <div v-for="skill in category.skills" :key="skill.name">
              <div class="mb-2 flex justify-between">
                <span class="text-slate-lighter">{{ skill.name }}</span>
                <span class="font-mono text-sm text-slate">{{ skill.proficiency }}%</span>
              </div>
              <div class="h-2 overflow-hidden rounded-full bg-navy-light">
                <div class="h-full rounded-full bg-highlight" :style="{ width: `${skill.proficiency}%` }" />
              </div>
            </div>
          </div>
        </div>

        <div class="animate-slideUp col-span-1 opacity-0 lg:col-span-2" style="animation-delay: 0.6s">
          <h3 class="mb-6 font-mono text-xl text-highlight">Core Competencies</h3>
          <div class="grid grid-cols-2 gap-4 md:grid-cols-4">
            <div
              v-for="competency in competencies"
              :key="competency"
              class="rounded border border-slate/20 bg-navy-light px-4 py-3 text-center transition-all duration-300 hover:border-highlight"
            >
              {{ competency }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
