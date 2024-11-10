<template>
    <div v-if="isVisible" class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-75">
      <div class="bg-gray-900 max-w-xl w-full rounded-lg overflow-hidden text-white">
        <!-- Modal Header -->
        <div class="flex justify-between items-center p-4 bg-gray-800 text-white">
          <h2 class="text-sm uppercase tracking-wider font-semibold">Course Preview</h2>
          <button @click="$emit('close')" class="text-white text-xl">&times;</button>
        </div>
  
        <!-- Modal Body -->
        <div class="p-6">
          <h3 class="text-lg font-bold mb-4">{{ videoTitle }}</h3>
          <!-- Video Player -->
          <div class="mb-6">
            <iframe
              width="100%"
              height="315"
              src="https://www.youtube.com/embed/kbZejnPXyLM?si=ZAiOfbUYLoZSSesz"
              title="YouTube video player"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
            ></iframe>
          </div>
          
          <p class="text-sm font-semibold mb-4">Free Sample Videos:</p>
          <div class="bg-gray-800 p-2 rounded-lg max-h-60 overflow-y-auto">
            <div v-for="(video, index) in sampleVideos" :key="index" class="flex items-center justify-between p-2 hover:bg-gray-700 rounded-md cursor-pointer">
              <div class="flex items-center space-x-3">
                <img :src="video.thumbnail" alt="Thumbnail" class="w-12 h-8 rounded-md" />
                <span :class="{ 'text-purple-400 font-semibold': videoTitle === video.title }" class="text-sm">{{ video.title }}</span>
              </div>
              <span class="text-sm text-gray-400">{{ video.duration }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const props = defineProps(['isVisible', 'videoTitle', 'videoUrl']);
  
  const sampleVideos = ref([
    { title: "Learn Figma - UI/UX Design Essential Training", thumbnail: "/thumbnails/video1.jpg", duration: "01:35" },
    { title: "Introduction to the Course", thumbnail: "/thumbnails/video2.jpg", duration: "00:34" },
    { title: "Using the Exercise Files", thumbnail: "/thumbnails/video3.jpg", duration: "01:06" },
    { title: "Section Introduction", thumbnail: "/thumbnails/video4.jpg", duration: "00:18" },
    { title: "What is Figma?", thumbnail: "/thumbnails/video5.jpg", duration: "00:48" },
    // Add additional sample video entries as needed
  ]);
  </script>
  
  <style scoped>
  /* Style for modal background and popup */
  .fixed {
    background: rgba(0, 0, 0, 0.75);
  }
  .text-white {
    color: #fff;
  }
  .bg-gray-900 {
    background-color: #121213;
  }
  .bg-gray-800 {
    background-color: #2b2b2b;
  }
  .bg-gray-100 {
    background-color: #f7fafc;
  }
  .text-purple-400 {
    color: #9f7aea;
  }
  .hover\:bg-gray-700:hover {
    background-color: #4a5568;
  }
  </style>
  