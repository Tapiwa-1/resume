<template>
  <div class="flex flex-col gap-y-3">
    <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Work Experience</h2>

    <!-- Loop Through Experience Items -->
    <Disclosure v-for="(job, index) in jobs" :key="index">
      <template #default="{ open }">
        <div>
          <!-- Trigger -->
          <DisclosureButton class="w-full flex justify-between items-center cursor-pointer rounded-lg bg-card text-card-foreground hover:bg-gray-100 hover:bg-opacity-35 transition">
            <!-- Left Side: Job Title and Duration -->
            <div class="flex flex-col items-start flex-grow">
              <h3 class="font-semibold text-md md:text-md text-gray-600">{{ job.company }}</h3>
              <p class="text-sm text-gray-500">{{ job.duration }}</p>
            </div>

            <!-- Arrow Icon -->
            <div
              class="transform transition-transform duration-300"
              :class="{ 'rotate-180': open, 'bounce-animation': !open }"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 text-gray-600"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  fill-rule="evenodd"
                  d="M5.293 9.707a1 1 0 011.414 0L10 13.086l3.293-3.379a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
          </DisclosureButton>

          <!-- Expanding Content -->
          <DisclosurePanel class="overflow-hidden">
            <div class="p-4 text-md md:text-md text-gray-600 slide-down" :class="{ 'slide-up': open }">
              {{ job.description }}
            </div>
          </DisclosurePanel>
        </div>
      </template>
    </Disclosure>
  </div>
</template>
<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue';

const jobs = [
  {
    company: 'Ministry of Local Government | IT Intern',
    duration: 'August 2022 - July 2023',
    description:
      'Provided technical support to ministry staff, troubleshooting hardware and software issues, resolving network connectivity problems, and addressing user queries promptly and efficiently.',
  },
  {
    company: 'Xash Pay Zimbabwe | FullStack Developer',
    duration: 'April 2025 - Present',
    description:
      'Develop and maintain features across all Xash platforms, including Fluxr. Collaborate with cross-functional teams to enhance system design and user experience. Resolve software issues, support non-technical staff, and ensure product stability through coordinated development efforts',
  },
  // Add more jobs here...
];
</script>
