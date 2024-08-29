<template>
  <div class="flex min-h-0 flex-col gap-y-3">
    <div>
      <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Skills</h2>
    </div>
    <div class="flex flex-wrap gap-1">
      <div v-for="skill in skills" :key="skill.name" class="skill-item inline-flex items-center cursor-pointer rounded-md border px-2.5 py-2 text-xs font-semibold transition-transform focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2 border-transparent bg-primary text-primary-foreground shadow hover:bg-primary/80 m-1">
        <!-- Icon based on the skill -->
        <font-awesome-icon :icon="skill.icon" class="mr-2" />
        {{ skill.name }}
      </div>
    </div>
  </div>
</template>

<script setup>
// Import necessary FontAwesome components
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faHtml5, faCss3Alt, faJs, faPhp, faPython, faVuejs, faNodeJs, faDocker } from '@fortawesome/free-brands-svg-icons'
import { faCode } from '@fortawesome/free-solid-svg-icons'

// Register the FontAwesomeIcon component
const skills = [
  { name: "HTML", icon: faHtml5 },
  { name: "CSS", icon: faCss3Alt },
  { name: "Javascript", icon: faJs },
  { name: "Php", icon: faPhp },
  { name: "C/C++", icon: faCode },
  { name: "Python", icon: faPython },
  { name: "C#", icon: faCode },
  { name: "Tailwind", icon: faCode },
  { name: "VueJS", icon: faVuejs },
  { name: "NuxtJS", icon: faVuejs },
  { name: "AngularJS", icon: faCode },
  { name: "Node", icon: faNodeJs },
  { name: "Express", icon: faNodeJs },
  { name: "Laravel", icon: faPhp },
  { name: "Azure", icon: faCode },
  { name: "Docker", icon: faDocker }
];
</script>

<style>
.skill-item {
  transition: transform 0.3s ease-in-out, filter 0.3s ease-in-out;
}

.skill-item:hover {
  transform: scale(1.1);
  filter: brightness(1.2);
}
</style>
