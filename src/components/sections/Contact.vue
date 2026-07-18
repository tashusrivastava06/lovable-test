<script setup>
function handleSubmit() {
  // No backend wired up yet — placeholder for a future integration.
}
</script>

<template>
  <section id="contact" class="bg-navy px-6 py-20">
    <div class="container mx-auto max-w-5xl">
      <div class="mb-12 animate-slideUp text-center opacity-0" style="animation-delay: 0.2s">
        <p class="mb-2 font-mono text-highlight">05. What's Next?</p>
        <h2 class="mb-4 text-4xl font-semibold text-slate-lightest">Get In Touch</h2>
        <p class="mx-auto max-w-2xl text-slate-light">
          I'm currently open to new opportunities and collaborations. Whether you have a question or just want to say hello,
          I'll do my best to get back to you!
        </p>
      </div>

      <div class="grid grid-cols-1 items-center gap-10 md:grid-cols-2">
        <div class="animate-slideUp opacity-0" style="animation-delay: 0.4s">
          <div class="rounded-lg border border-slate/20 bg-navy-light p-8">
            <h3 class="mb-6 text-2xl font-semibold text-slate-lightest">Contact Information</h3>

            <div class="space-y-6">
              <div class="flex items-start">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mt-1 mr-4 text-highlight">
                  <rect width="20" height="16" x="2" y="4" rx="2" /><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7" />
                </svg>
                <div>
                  <p class="mb-1 font-mono text-sm text-slate">Email</p>
                  <a href="mailto:tashusrivastava06@gmail.com" class="text-slate-lighter transition-colors hover:text-highlight">
                    tashusrivastava06@gmail.com
                  </a>
                </div>
              </div>

              <div class="flex items-start">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mt-1 mr-4 text-highlight">
                  <path d="M13.832 16.568a1 1 0 0 0 1.213-.303l.355-.465A2 2 0 0 1 17 15h3a2 2 0 0 1 2 2v3a2 2 0 0 1-2 2A18 18 0 0 1 2 4a2 2 0 0 1 2-2h3a2 2 0 0 1 2 2v3a2 2 0 0 1-.8 1.6l-.468.351a1 1 0 0 0-.292 1.233 14 14 0 0 0 6.392 6.384" />
                </svg>
                <div>
                  <p class="mb-1 font-mono text-sm text-slate">Phone</p>
                  <a href="tel:+918130465143" class="text-slate-lighter transition-colors hover:text-highlight">
                    +91 8130465143
                  </a>
                </div>
              </div>

              <div class="flex items-start">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="mt-1 mr-4 text-highlight">
                  <path d="M20 10c0 4.993-5.539 10.193-7.399 11.799a1 1 0 0 1-1.202 0C9.539 20.193 4 14.993 4 10a8 8 0 0 1 16 0" />
                  <circle cx="12" cy="10" r="3" />
                </svg>
                <div>
                  <p class="mb-1 font-mono text-sm text-slate">Location</p>
                  <p class="text-slate-lighter">
                    Apex Golf Avenue<br />
                    Greater Noida West<br />
                    Gautam Buddh Nagar, UP 201308
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="animate-slideUp opacity-0" style="animation-delay: 0.6s">
          <form class="space-y-6" @submit.prevent="handleSubmit">
            <div class="grid grid-cols-1 gap-6 md:grid-cols-2">
              <div>
                <label for="name" class="mb-2 block font-mono text-sm text-slate-lighter">
                  Name
                </label>
                <input
                  id="name"
                  type="text"
                  class="w-full rounded border border-slate/20 bg-navy-light p-3 text-slate-lighter transition-colors focus:border-highlight focus:outline-none"
                  placeholder="Your Name"
                />
              </div>

              <div>
                <label for="email" class="mb-2 block font-mono text-sm text-slate-lighter">
                  Email
                </label>
                <input
                  id="email"
                  type="email"
                  class="w-full rounded border border-slate/20 bg-navy-light p-3 text-slate-lighter transition-colors focus:border-highlight focus:outline-none"
                  placeholder="Your Email"
                />
              </div>
            </div>

            <div>
              <label for="subject" class="mb-2 block font-mono text-sm text-slate-lighter">
                Subject
              </label>
              <input
                id="subject"
                type="text"
                class="w-full rounded border border-slate/20 bg-navy-light p-3 text-slate-lighter transition-colors focus:border-highlight focus:outline-none"
                placeholder="Subject"
              />
            </div>

            <div>
              <label for="message" class="mb-2 block font-mono text-sm text-slate-lighter">
                Message
              </label>
              <textarea
                id="message"
                rows="6"
                class="w-full rounded border border-slate/20 bg-navy-light p-3 text-slate-lighter transition-colors focus:border-highlight focus:outline-none"
                placeholder="Your Message"
              />
            </div>

            <button
              type="submit"
              class="cursor-pointer rounded border border-highlight bg-transparent px-8 py-6 font-mono text-highlight transition-all duration-300 hover:bg-highlight/10"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>
