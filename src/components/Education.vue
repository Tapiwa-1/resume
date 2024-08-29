<template>
  <div class="flex flex-col gap-y-3">
    <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Education</h2>

    <!-- School Item -->
    <div>
      <a class="block cursor-pointer" @click="toggleSchool">
        <div class="rounded-lg bg-card text-card-foreground flex  items-center hover:bg-gray-100 hover:bg-opacity-35 transition justify-between">
          <!-- Left Side: Degree and School -->
          <div class="flex flex-col flex-grow">
            <h3 class="font-semibold text-md md:text-md text-gray-600">
              Bachelor of Science in Information Security and Assurance
            </h3>
            
            <p class="text-sm md:text-sm text-gray-500">
              Harare Institute of Technology, Harare
            </p>
            <p class="text-sm text-gray-600">
              August 2020 - May 2024
            </p>
          </div>

          <!-- Arrow Icon -->
          <div
            class="ml-2 flex-shrink-0 transform transition-transform duration-300"
            :class="{ 'rotate-180': isExpandedSchool, 'bounce-animation': !isExpandedSchool }"
          >
            <!-- Arrow Down Icon -->
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-600" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5.293 9.707a1 1 0 011.414 0L10 13.086l3.293-3.379a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </div>
        </div>

        <!-- Expanding Content -->
        <transition name="expand">
          <div v-if="isExpandedSchool" class="p-4">
            <h4 class="font-semibold text-md text-gray-600">Core Principles:</h4>
            <ul class="list-disc list-inside text-sm md:text-sm text-gray-500">
              <li>Confidentiality: Ensuring information access only to authorized users.</li>
              <li>Integrity: Maintaining information accuracy and completeness.</li>
              <li>Availability: Guaranteeing authorized users' timely access to information.</li>
            </ul>

            <h4 class="font-semibold text-md text-gray-600 mt-2">Key Areas:</h4>
            <ul class="list-disc list-inside text-sm md:text-sm text-gray-500">
              <li>Network Security: Protecting networks from unauthorized access.</li>
              <li>Risk Management: Identifying and mitigating security risks.</li>
              <li>Incident Response: Investigating and responding to cyberattacks.</li>
              <li>Information Security Law: Understanding legal and ethical implications.</li>
              <li>Software Development: Secure coding practices and secure application testing.</li>
              <li>System Administration: System hardening, patch management, and security monitoring.</li>
              <li>IT Auditing: Understanding security regulations, conducting risk assessments, and evaluating security controls.</li>
              <li>IT Support: Incident response procedures and user education on security best practices.</li>
            </ul>

            <h4 class="font-semibold text-md text-gray-600 mt-2">Benefits:</h4>
            <ul class="list-disc list-inside text-sm md:text-sm text-gray-500">
              <li>In-depth cybersecurity knowledge and practices.</li>
              <li>Ability to design, implement, and maintain security solutions.</li>
              <li>Expertise in protecting sensitive data and networks.</li>
              <li>Preparation for a successful cybersecurity career.</li>
            </ul>
          </div>
        </transition>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isExpandedSchool = ref(false);

const toggleSchool = () => {
  isExpandedSchool.value = !isExpandedSchool.value;
};
</script>

<style>
/* Transition for expanding and collapsing content */
.expand-enter-active,
.expand-leave-active {
  transition: max-height 0.3s ease, opacity 0.3s ease;
}
.expand-enter,
.expand-leave-to {
  max-height: 0;
  opacity: 0;
}
.expand-enter-to,
.expand-leave {
  max-height: 1000px; /* Adjust according to content length */
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
