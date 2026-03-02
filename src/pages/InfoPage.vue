<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Leslie Guillen',
  avatar:
    'https://img.freepik.com/premium-photo/cartoon-girl-with-glasses-brown-hair-generative-ai_1034986-18129.jpg',
  about:
    ' Ambitious Cybersecurity graduate with a strong foundation in network security, threat analysis, and ethical hacking. Proficient in Python and Linux certified. Eager to apply hands-on skills in vulnerablility assessment and incident response to protect organizational assets.',
  skills: ['networking', 'cloud security', 'Linux', 'Node.js', 'Tailwind CSS'],
  email: 'lguille6@stu.southtexascollege.edu',
  location: 'Edinburg, Tx',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="hover-text-pink-400 my-8 self-start text-pink-400 underline-offset-4 transition-colors duration-300 hover:underline"
    >
      ⬅️ Back to Links
    </RouterLink>

    <!-- Profile Card -->
    <div
      class="w-full max-w-lg rounded-2xl border border-pink-600 bg-gray-900 p-6 shadow-xl shadow-pink-900/50 sm:p-8"
    >
      <!-- Header -->
      <div class="mb=6 sm:glx-row flex flex-col items-center text-center sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-pink-500 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-white">📍{{ bio.location }}</p>
        </div>
      </div>

      <!-- About Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">About</h2>
        <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
      </div>

      <!-- Skill Section-->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Skills</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-red-300/50 px-3 py-1 text-sm text-white"
          >
            {{ skill }}
          </span>
        </div>
      </div>

      <!-- Contact -->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Get in Touch</h2>
        <a
          :href="`mailto:${bio.email}`"
          class="group hover-pink-500/40 inline-flex items-center gap-2 rounded-xl bg-pink-500 px-6 py-3 font-medium text-white shadow-lg shadow-pink-500/30 transition-all duration-200 hover:scale-105 hover:bg-pink-600 hover:shadow-xl active:scale-95"
        >
          <svg
            data-slot="icon"
            fill="none"
            stroke-width="1.5"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
            class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
            ></path>
          </svg>
          Send Email
        </a>
      </div>
    </div>
  </main>
</template>
