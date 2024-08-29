<template>
  <AnimatedBackground/>
  <Spinner v-if="loading" />
  <div class=" relative" v-else id="app">
   
    <header  class="shadow-md">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <!-- Logo -->
      <div class="flex items-center space-x-3">
        <a href="/resume" class="flex items-center">
          <span :class="{'text-xl font-semibold ml-2': true, 'text-gray-900': !isDarkMode, 'text-white': isDarkMode}">Tapiwa Motsi</span>
        </a>
      </div>

      <!-- Navigation Links -->
      <nav class="hidden md:flex space-x-8" :class="{'text-gray-700': !isDarkMode, 'text-gray-300': isDarkMode}">
        <a href="#about" class="hover:text-green-600">About</a>
        <a href="#work" class="hover:text-green-600">Work</a>
        <a href="#education" class="hover:text-green-600">Education</a>
        <a href="#skills" class="hover:text-green-600">Skills</a>
        <a href="#projects" class="hover:text-green-600">Projects</a>
      </nav>

      <!-- Dropdown for smaller screens -->
      <div class="md:hidden flex items-center">
        <button @click="toggleMobileMenu" class="text-gray-700 focus:outline-none">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
          </svg>
        </button>
      </div>

      <!-- Right-aligned links (Social icons, GitHub link, and Dark Mode Toggle) -->
      <div class="hidden md:flex space-x-4 items-center">
        <a href="https://twitter.com/vuejs" aria-label="Twitter" :class="{'text-gray-700': !isDarkMode, 'text-gray-300': isDarkMode}">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="..."></path></svg>
        </a>
        <a href="https://github.com/vuejs/vue" aria-label="GitHub" :class="{'text-gray-700': !isDarkMode, 'text-gray-300': isDarkMode}">
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="..."></path></svg>
        </a>
        <div class="hover:text-green-600 cursor-pointer">
          v1.0.0
        </div>
     
      </div>
    </div>

    <!-- Mobile Menu -->
    <div id="mobile-menu" v-if="isMobileMenuOpen" class="md:hidden">
      <nav class="flex flex-col space-y-2 px-4 py-3" :class="{'text-gray-700': !isDarkMode, 'text-gray-300': isDarkMode}">
        <a href="#about" class="hover:text-green-600">About</a>
        <a href="#work" class="hover:text-green-600">Work</a>
        <a href="#education" class="hover:text-green-600">Education</a>
        <a href="#skills" class="hover:text-green-600">Skills</a>
        <a href="#projects" class="hover:text-green-600">Projects</a>
      </nav>
    </div>
  </header>

    <!-- Landing Section -->
    <section class="text-center mt-20">
      <h1 class="text-4xl md:text-8xl font-bold bg-gradient-to-r from-green-900 to-blue-400 text-transparent bg-clip-text">
        Tapiwa Motsi
      </h1>
      <p class="text-xl md:text-4xl font-extrabold text-gray-600 mt-4">
        <span>Is a {{ currentText }}</span>
      </p>

      <!-- Buttons -->
      <div class="mt-9 flex justify-center space-x-4 ">
        <a href="../resume/assets/resume.pdf" download class="bg-green-600 text-white px-6 py-2 rounded-md shadow hover:bg-green-700 transition duration-300">
          Download CV
        </a>
        <a href="#about" class="bg-gray-200 text-gray-800 px-6 py-2 rounded-md shadow hover:bg-gray-300 transition duration-300">
          View About
        </a>
      </div>
    </section>

        <!-- Descriptive Text Section -->
    <section class=" mt-20 px-4 md:px-0  md:pt-10">
      <TopSection :texts="topText"/>
    </section>

    <!-- About Me Section -->
    <section id="about" class="mt-12 md:mt-16 px-4 md:px-0">
      <div class="max-w-4xl mx-auto text-justify ">
        <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">About Me</h2>
        <p class="text-md md:text-md text-gray-700">
          Tapiwa Motsi, a young man very passionate about everything Information Technology and Information Security, whose passion lies in creating secure web applications, system administration, cloud computing, cybersecurity, and DevOps.
        </p>
      </div>
    </section>
    <!-- Work Experience -->
      <section id="work"class="mt-12 md:mt-16 px-4 md:px-0">
        <Work/>
      </section>

       <!-- School Experience -->
  <section id="education"class="mt-12 md:mt-16 px-4 md:px-0">
    <div class="max-w-4xl mx-auto text-justify">
      <Education/>
    </div>
    
  </section>
  <section id="skills"class="mt-12 md:mt-16 px-4 md:px-0">
    <div class="max-w-4xl mx-auto text-justify">
      <Skills/>
    </div>
     
  </section>
  <section id="projects" class="mt-12 md:mt-16 px-4 md:px-0">
    <div class="max-w-4xl mx-auto text-justify">
      <Projects/>
    </div>
   
  </section>
  <Footer/>
  </div>
  
</template>
<script setup>
import { ref, onMounted } from 'vue';
import TopSection from './components/TopSection.vue';
import Work from './components/Work.vue'
import Education from './components/Education.vue';
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue'
import Footer from './components/Footer.vue'
import Spinner from './components/Spinner.vue';
import AnimatedBackground from './components/AnimatedBackground.vue';
const texts = [
  'Software Engineer',
  'System Administrator',
  'System Security Analyst',
];

const loading = ref(true);

onMounted(() => {
  setTimeout(() => {
    loading.value = false;
  }, 3000); // 3 seconds
});
const topText = ref([
  {
    id: 1,
    heading: "Software Engineering",
    description: "Crafting high-performance, secure applications that leverage cutting-edge technologies to optimize efficiency and user experience. By staying abreast of industry trends and best practices.",
  },
  {
    id: 4,
    heading: "System Administration",
    description: "Experienced system administrator specializing in optimizing performance, security, and IT support. Leveraging advanced tools and methodologies to deliver efficient solutions.",
  },
  {
    id: 3,
    heading: "System Security Analyst",
    description: "Experienced security analyst specializing in threat intelligence, vulnerability assessment, and incident response. Committed to safeguarding sensitive information and ensuring organizational resilience.",
  },
]);

const currentText = ref('');
let currentIndex = 0;
let charIndex = 0;




const typeText = () => {
  if (charIndex < texts[currentIndex].length) {
    currentText.value += texts[currentIndex].charAt(charIndex);
    charIndex++;
    setTimeout(typeText, 100);
  } else {
    setTimeout(() => {
      currentIndex = (currentIndex + 1) % texts.length;
      currentText.value = '';
      charIndex = 0;
      setTimeout(typeText, 500);
    }, 2000);
  }
};

onMounted(() => {
  typeText();
});

// State for mobile menu
const isMobileMenuOpen = ref(false);

// Function to toggle mobile menu
const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>
<style scoped>
.blinking-cursor {
  font-weight: bold;
  font-size: 2.5rem;
  color: #2d3748;
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  from, to { opacity: 1; }
  50% { opacity: 0; }
}


</style>
