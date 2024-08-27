<template>
    <div class="flex flex-col gap-y-3">
          <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Work Experience</h2>

          <!-- Experience Item -->
          <div>
            <a
              class="block cursor-pointer "
              @click="toggleDetails"
            >
              <div class="rounded-lg bg-card text-card-foreground flex p-4 items-center">
                <!-- Left Side: Company Name -->
                <div class="flex-grow">
                  <h3 class="font-semibold text-md md:text-md text-gray-600">{{ job.company }}</h3>
                </div>
                
                <!-- Right Side: Duration -->
                <div class="text-md md:text-md text-gray-600">
                  {{ job.duration }}
                </div>
              </div>

              <!-- Expanding Content -->
              <transition name="expand">
                <div v-if="isExpanded" class="p-4">
                  <p class="text-md md:text-md text-gray-600">
                    {{ job.description }}
                  </p>
                </div>
              </transition>
            </a>
          </div>

        
        </div>

</template>

<script setup>
import { ref, onMounted } from 'vue';
const isExpanded = ref(false);


const job = {
  company: 'IT Intern',
  duration: 'August 2022 - July 2023',
  description:
    'Provide technical support to ministry staff, troubleshooting hardware and software issues, resolving network connectivity problems, and addressing user queries promptly and efficiently',
};

const toggleDetails = () => {
  isExpanded.value = !isExpanded.value;
};
</script>

<style>
/* Transition for expanding and collapsing content */
.expand-enter-active, .expand-leave-active {
  transition: max-height 0.1s ease;
}
.expand-enter, .expand-leave-to {
  max-height: 0;
  opacity: 0;
}
.expand-enter-to, .expand-leave {
  max-height: 100px; /* Adjust according to content length */
  opacity: 1;
}
</style>