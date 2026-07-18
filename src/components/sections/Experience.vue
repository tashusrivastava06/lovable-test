<script setup>
import { ref } from 'vue'

const activeTab = ref(0)

const jobs = [
  {
    company: 'CAASTLE.COM',
    title: 'Principal Engineer',
    duration: 'Oct 2017 - Present',
    responsibilities: [
      'Lead development teams, ensuring implementation of best practices and high-quality code',
      'Define scalable frontend architectures and collaborate with UX/UI designers and backend teams',
      'Optimize website performance for faster load times and responsiveness',
      'Coordinate with stakeholders to ensure timely delivery of frontend features aligned with business goals',
      'Mentor junior developers and conduct code reviews',
    ],
    projects: [
      {
        name: 'Storefront Builder',
        description: 'Created a templated, configurable system for rapid onboarding of D2C brands, automating CSS/text variable integration via scripts. Built with React and SASS for scalable, efficient client setups.',
      },
      {
        name: 'Business Associates (BA) Asset Collection Tool',
        description: 'Designed and developed a React-based tool with real-time preview, enabling quick onboarding of brand assets with dynamic website updates.',
      },
      {
        name: 'Borrow Feature',
        description: 'Launched a "Borrow" option with brands like Elyse Walker & Altuzarra, enhancing customer engagement through seamless site integration.',
      },
    ],
  },
  {
    company: 'SHOPCLUES.COM',
    title: 'Sr. UI Developer',
    duration: 'May 2015 - October 2017',
    responsibilities: [
      'Developed REACH mobile & desktop web platform for online payment acceptance',
      'Built responsive front-end with AngularJS, REST API integration, and HTML5/CSS3 (LESS)',
      'Designed and implemented responsive, cross-browser components for mobile website',
      'Collaborated with backend teams to maintain design consistency',
      'Single-handedly designed mobile UI for Store Manager using HTML5, CSS3, jQuery, and Google Material Design',
    ],
  },
  {
    company: 'TATA CONSULTANCY SERVICES',
    title: 'UI Developer',
    duration: 'January 2014 - April 2015',
    responsibilities: [
      'Served as UI/UX lead for AMEX, handling multiple projects',
      'Built responsive pages using AngularJS, HTML5, CSS3, Ajax, Bootstrap',
      'Acted as sole UI developer for Sears; designed responsive UI screens and dynamic data charts',
      'Enhanced existing Walgreens applications with new UI screens',
      'Developed universal fluid layout framework for consistent theming across devices',
    ],
  },
  {
    company: 'OMNI-NET TECHNOLOGIES',
    title: 'Web/UI Designer',
    duration: 'August 2010 - October 2013',
    responsibilities: [
      'Independently developed numerous government websites from scratch',
      'Designed website templates in Photoshop and converted them into fully functional live sites',
      'Managed over 60+ live government and private websites',
      'Completed notable projects including IIM Lucknow, UP Tourism, UP Police, UPTU, and MahaKumbh 2013',
    ],
  },
]
</script>

<template>
  <section id="experience" class="bg-navy-light px-6 py-20">
    <div class="container mx-auto max-w-5xl">
      <h2 class="section-heading">
        <span class="number">02.</span> Where I've Worked
      </h2>

      <div class="grid grid-cols-1 gap-4 md:grid-cols-12">
        <!-- Tab list -->
        <div class="mb-6 md:col-span-3 md:mb-0">
          <div class="scrollbar-hide flex overflow-x-auto md:flex-col md:overflow-visible">
            <button
              v-for="(job, i) in jobs"
              :key="job.company"
              class="cursor-pointer border-b-2 px-4 py-3 text-left font-mono text-sm whitespace-nowrap transition-all duration-300 md:border-b-0 md:border-l-2 md:whitespace-normal"
              :class="activeTab === i
                ? 'border-highlight bg-navy-light/30 text-highlight'
                : 'border-slate/20 text-slate hover:bg-navy-light/10 hover:text-highlight'"
              @click="activeTab = i"
            >
              {{ job.company }}
            </button>
          </div>
        </div>

        <!-- Tab content -->
        <div class="animate-slideUp opacity-0 md:col-span-9" style="animation-delay: 0.2s" :key="activeTab">
          <h3 class="mb-1 text-2xl font-semibold">
            {{ jobs[activeTab].title }} <span class="text-highlight">@ {{ jobs[activeTab].company }}</span>
          </h3>
          <p class="mb-6 font-mono text-sm text-slate">{{ jobs[activeTab].duration }}</p>

          <ul class="mb-8 space-y-4">
            <li v-for="(item, i) in jobs[activeTab].responsibilities" :key="i" class="flex">
              <span class="mr-2 pt-1 text-highlight">▹</span>
              <span>{{ item }}</span>
            </li>
          </ul>

          <div v-if="jobs[activeTab].projects">
            <h4 class="mb-3 text-lg font-semibold text-slate-lightest">Key Projects:</h4>
            <div class="space-y-4">
              <div v-for="project in jobs[activeTab].projects" :key="project.name" class="rounded bg-navy-dark p-5">
                <h5 class="mb-2 font-mono text-highlight">{{ project.name }}</h5>
                <p class="text-sm text-slate-light">{{ project.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
