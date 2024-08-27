<template>
    <div class="flex min-h-0 flex-col gap-y-3">
      <div style="opacity: 1; filter: blur(0px); transform: translateY(-6px) translateZ(0px);">
        <h2 class="text-xl md:text-xl font-bold text-gray-800 mb-4">Skills</h2>
      </div>
      <div class="flex flex-wrap gap-1">
       
        <div class="flex flex-wrap gap-1">
          <div style="opacity: 1; filter: blur(0px); transform: translateY(-6px) translateZ(0px);">
            <div  v-for="skill in skills" :key="skill.name"  class="inline-flex items-center rounded-md border px-2.5 py-2 text-xs font-semibold transition-colors focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2 border-transparent bg-primary text-primary-foreground shadow hover:bg-primary/80 m-1">{{ skill.name }} </div>
          </div>
        </div>
      </div>
    </div>
</template>
<script setup>
// import { ref } from "vue";

const skills = [
    {name: "HTML"},
    {name: "CSS"},
    {name: "Javascript"},
    {name: "Php"},
    {name: "C/C++"},
    {name: "Python"},
    {name: "C#"},
    {name: "Tailwind"},
    {name: "VueJS"},
    {name: "NuxtJS"},
    {name: "AngularJS"},
    {name: "Node"},
    {name: "Express"},
    {name: "Laravel"},
    {name: "Azure"},
    {name: "Docker"},
]
</script>