<template>
    <section id="projects" class="max-w-7xl mx-auto">
        <div class="max-w-4xl mx-auto text-justify">
            <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Projects</h2>
            <h2 class="text-xl md:text-lg font-bold text-gray-800 mb-4">Check out my latest work</h2>
            <p class="text-md md:text-md text-gray-700">
                I've worked on a variety of projects, from simple websites to complex web applications. Here are a few of my favorites:
            </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div v-for="project in projects" :key="project.id" class="group relative rounded-lg shadow-lg overflow-hidden">
                <img class="w-full h-48 object-cover" :src="project.src" :alt="project.name">
                
                <div class="absolute inset-0 bg-gradient-to-b from-transparent to-black opacity-50"></div>
                
                <div class="absolute inset-0 flex flex-col justify-end p-6 transition-opacity duration-300">
                    <h3 class="text-white text-lg font-semibold">{{ project.name }}</h3>
                    <div class="mt-4">
                        <a :href="project.link" target="_blank" class="bg-green-600 text-white px-6 py-2 rounded-md shadow hover:bg-green-700 transition duration-300">
                            View on GitHub
                        </a>
                    </div>
                </div>
                
                <!-- Overlay on hover -->
                <a :href="project.link" class="absolute inset-0 bg-black bg-opacity-80 text-white flex flex-col items-center justify-center text-center px-4 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                    <p class="text-sm">{{ project.description }}</p>
                    <p class="text-xs mt-2 font-light">Tech Stack: {{ project.techStack }}</p>
                </a>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';

const projects = ref([
    {
        id: 1,
        name: "Online Procurement System 2024",
        description: "A web-based platform for managing procurement processes efficiently.",
        techStack: "Laravel, Vue.js, Tailwind CSS, MySQL",
        link: "https://github.com/Tapiwa-1/procurement",
        src: "https://github.com/Tapiwa-1/procurement/raw/main/public/img/4.png"
    },
    {
        id: 2,
        name: "G-Drive System 2024",
        description: "AI web-based platform for storing and managing pictures using vector databases and semantic search",
        techStack: "Vue.js, Firebase, Tailwind CSS, Python, Chromadb",
        link: "https://www.linkedin.com/posts/tapiwamotsi_ai-machinelearning-imageprocessing-activity-7249681427074629632-mzWI?utm_source=share&utm_medium=member_desktop",
        src: "https://github.com/Tapiwa-1/Tapiwa-1/blob/main/img.jpeg?raw=true"
    },
    {
        id: 3,
        name: "Traditional Leaders Portal 2022",
        description: "A portal for traditional leaders to manage governance and local affairs.",
        techStack: "Laravel, Vue.js, Bootstrap, MySQL",
        link: "https://github.com/Tapiwa-1/localmlg",
        src: "https://github.com/Tapiwa-1/resume/blob/main/src/assets/procrument.jpeg?raw=true"
    },
    {
        id: 4,
        name: "Harare Institute of Technology Clinic System 2021",
        description: "A hospital management system for HIT Clinic to streamline operations.",
        techStack: "PHP.js, Bootstrap, MySQL",
        link: "https://github.com/Tapiwa-1/hospital-system",
        src: "https://github.com/Tapiwa-1/Tapiwa-1/raw/main/hitclinic-main.png"
    }
]);
</script>
