<template>
  <div class="flex flex-col gap-y-3">
    <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Work Experience</h2>

    <!-- Experience Item -->
    <Disclosure>
      <template #default="{ open }">
        <div>
          <!-- Trigger -->
          <DisclosureButton class="w-full flex justify-between items-center cursor-pointer rounded-lg bg-card text-card-foreground hover:bg-gray-100 hover:bg-opacity-35 transition">
            <!-- Left Side: Job Title and Duration -->
            <div class="flex flex-col items-start flex-grow">
              <!-- Job Title -->
              <h3 class="font-semibold text-md md:text-md text-gray-600">{{ job.company }}</h3>
              <!-- Job Duration -->
              <p class="text-sm text-gray-500">{{ job.duration }}</p>
            </div>

            <!-- Arrow Icon -->
            <div
              class="transform transition-transform duration-300"
              :class="{ 'rotate-180': open, 'bounce-animation': !open }"
            >
              <!-- Arrow Down Icon -->
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

const job = {
  company: 'Ministry of Local Government | IT Intern',
  duration: 'August 2022 - July 2023',
  description: 'Provide technical support to ministry staff, troubleshooting hardware and software issues, resolving network connectivity problems, and addressing user queries promptly and efficiently',
};
</script>

<style>
/* Slide Animation */
.slide-down {
  max-height: 0;
  opacity: 0;
  transition: max-height 0.3s ease, opacity 0.3s ease;
}

.slide-up {
  max-height: 120px; /* Adjust according to the maximum content size */
  opacity: 1;
}

/* Bounce Animation */
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-8px);
  }
  60% {
    transform: translateY(-4px);
  }
}

.bounce-animation {
  animation: bounce 1s ease infinite;
}
</style>
