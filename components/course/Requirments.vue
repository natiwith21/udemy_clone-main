<!-- components/RequirementsAndDescription.vue -->
<template>
    <div class="max-w-screen-lg mx-auto mt-9 mb-8 px-4">
      <!-- Requirements Section -->
      <h2 class="text-xl font-bold mb-4">Requirements</h2>
      <ul class="list-disc list-inside text-gray-700 mb-6 d-text-sm">
        <li>Internet Access</li>
        <li>You should know your way around computer basics</li>
      </ul>
  
      <!-- Description Section -->
      <h2 class="text-xl font-bold mb-4">Description</h2>
      <div :class="{'line-clamp-5': !isExpanded}" class="text-gray-700 mb-2">
        <p class="d-text-sm">
          Figma is a very powerful application that runs online. There are virtually no platform boundaries when it comes to using Figma because you can design within a web browser or using their desktop application made for Windows and Macs. Figma is similar to Sketch and Adobe XD but is the more powerful of the three when it comes to team collaboration and responsive, fast-paced design.
        </p>
        <p v-if="isExpanded" class="mt-2 d-text-sm">
          This course will cover user interface designing using the powerful tools within Figma. In the first section, I'll cover the Figma interface and where you can find powerful tools like constraints to make your designs responsive, and components to build a library of design elements to use throughout your projects. I'll also go over real-time team collaboration and how you can use Figma to work closely with others in the same project.
        </p>
        <p v-if="isExpanded" class="mt-2 d-text-sm">
          Later on, I will guide you through designing and prototyping a "Chef's Recipes" App which will include multiple artboards, custom icon designs, editing images and text, and everything else you need to create a polished, realistic design.
        </p>
        <p v-if="isExpanded" class="mt-2 d-text-sm">
          Please join me as a beginner in design or as a seasoned UI/UX designer wanting to switch from other tools like Sketch or Adobe XD.
        </p>
  
        <!-- Who this course is for Section -->
        <div v-if="isExpanded" class="mt-4">
          <h2 class="text-xl font-bold mb-2">Who this course is for:</h2>
          <ul class="list-disc list-inside text-gray-700 d-text-sm">
            <li>User Interface designers</li>
            <li>Web Designers</li>
            <li>Graphic Designers</li>
            <li>UX Designers</li>
            <li>Beginners looking to get into the UI/UX field</li>
          </ul>
        </div>
      </div>
  
      <!-- Show More/Less Button -->
      <button @click="toggleDescription" class="text-blue-600 font-semibold mt-2 focus:outline-none">
        {{ isExpanded ? 'Show less' : 'Show more' }}
        <span :class="isExpanded ? 'rotate-180' : ''" class="transform transition-transform inline-block">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 inline" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
          </svg>
        </span>
      </button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const isExpanded = ref(false);
  
  function toggleDescription() {
    isExpanded.value = !isExpanded.value;
  }
  </script>
  
  <style scoped>
  .line-clamp-5 {
    display: -webkit-box;
    -webkit-line-clamp: 5;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  
  .d-text-sm {
    font-family: var(--font-stack-text);
    font-weight: 400;
    line-height: 1.4;
  
  }
  </style>
  