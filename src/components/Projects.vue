<template>
    <section id="projects" class="max-w-7xl mx-auto  ">
        <div class="max-w-4xl mx-auto text-justify ">
        <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Projects</h2>
        <h2 class="text-xl md:text-lg font-bold text-gray-800 mb-4">Check out my latest work</h2>
        <p class="text-md md:text-md text-gray-700">
          I've worked on a variety of projects, from simple websites to complex web applications. Here are a few of my favorites
        </p>
      </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div  v-for="project in projects" :key="project.id"  class="group relative rounded-lg shadow-lg overflow-hidden">
            <img class="w-full h-48 object-cover" :src="project.src" alt="Project 1">
            <div class="absolute inset-0 bg-gradient-to-b from-transparent to-black opacity-50"></div>
            <div class="absolute inset-0 p-6 flex flex-col justify-end">
                <h3 class="text-white text-lg font-semibold">{{ project.name }}</h3>
                <div class="mt-4">
                <a :href="project.link" class="bg-green-600 text-white px-6 py-2 rounded-md shadow hover:bg-green-700 transition duration-300">View on GitHub</a>
                </div>
            </div>
        </div>
  

  </div>
</section>

</template>

<script setup>
import { ref} from 'vue';

const projects = ref([
    {
        id:1,
        name:"Online Procrument System",
        link:"https://github.com/Tapiwa-1/procurement",
        src:"https://github.com/Tapiwa-1/procurement/raw/main/public/img/4.png"
    },
    {
        id:2,
        name:"Music Social App",
        description:"",
        link:"https://github.com/Tapiwa-1/music-app",
        src:"https://github.com/Tapiwa-1/Tapiwa-1/raw/main/social-media-app.png"

    },
    {
        id:3,
        name:"Tradional Leaders Portal",
        description:"",
        link:"https://github.com/Tapiwa-1/localmlg",
        src:"https://media.licdn.com/dms/image/v2/D4D2DAQHsrALDVrJHRw/profile-treasury-image-shrink_800_800/profile-treasury-image-shrink_800_800/0/1702473999343?e=1725343200&v=beta&t=6L2AIKNRqOYAXFNmpMquJ9pfcuiZzEps7noEt8I01t4"

    },
    {
        id:4,
        name:"Harare Insititute of Technology Clinic HiT Clinic",
        description:"",
        link:"https://github.com/Tapiwa-1/hospital-system",
        src:"https://media.licdn.com/dms/image/v2/D4D2DAQGgqe5PnCR2Sg/profile-treasury-image-shrink_800_800/profile-treasury-image-shrink_800_800/0/1702474144670?e=1725346800&v=beta&t=4MTPAOSSFvf7lna3LQ9FKycKjCsAkNqYt4YjGy7gWC8"

    }
])
</script>