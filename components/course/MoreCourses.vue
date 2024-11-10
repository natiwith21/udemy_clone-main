<!-- components/MoreCoursesByInstructor.vue -->
<template>
    <div class="border-t pt-6 max-w-screen-lg mx-auto mt-9 mb-8">
      <h2 class="text-xl font-bold mb-4">
        More Courses by <span class="text-purple-700">{{ instructorName }}</span>
      </h2>
  
      <!-- Course Cards -->
      <div class="grid grid-cols-3 gap-4">
        <div v-for="(course, index) in courses" :key="index" class="border p-4 rounded-lg">
          <img :src="course.image" alt="Course image" class="w-full h-40 object-cover rounded-md mb-3" />
  
          <!-- Course Details -->
          <p class="font-semibold text-base leading-tight mb-1">{{ course.title }}</p>
          <p class="text-gray-600 text-sm">{{ course.instructor }}</p>
          
          <!-- Rating, Duration, Lectures, and Level -->
          <div class="flex items-center text-sm text-gray-600 mb-2">
            <span class="font-semibold text-yellow-600 mr-1">{{ course.rating }}</span>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor" class="text-yellow-500 mr-1">
              <path d="m14.43 10l-1.47-4.84c-.29-.95-1.63-.95-1.91 0L9.57 10H5.12c-.97 0-1.37 1.25-.58 1.81l3.64 2.6l-1.43 4.61c-.29.93.79 1.68 1.56 1.09l3.69-2.8l3.69 2.81c.77.59 1.85-.16 1.56-1.09l-1.43-4.61l3.64-2.6c.79-.57.39-1.81-.58-1.81h-4.45z"/>
            </svg>
            <span>({{ course.reviews }})</span>
          </div>
          <p class="text-gray-600 text-sm">{{ course.duration }} • {{ course.lectures }} lectures • {{ course.level }}</p>
          
          <!-- Price -->
          <p class="font-semibold text-lg mt-2">{{ course.price }}</p>
        </div>
      </div>
  
      <!-- Report Abuse Button with Full Width -->
      <button class="w-full mt-4 px-6 py-2 border border-gray-400 rounded-md text-gray-600 hover:bg-gray-100">
        Report abuse
      </button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const instructorName = "Caleb Kingston";
  
  const courses = ref([
    {
      title: "Adobe XD UI/UX Design, prototype, and handoff...",
      instructor: "Caleb Kingston",
      rating: "4.6",
      reviews: "2,244",
      duration: "3.5 total hours",
      lectures: "52",
      level: "All Levels",
      price: "$54.99",
      image: "/logos/caleb.jpg" 
    },
    {
      title: "Learn Photoshop for iPad",
      instructor: "Caleb Kingston",
      rating: "4.4",
      reviews: "335",
      duration: "3 total hours",
      lectures: "39",
      level: "All Levels",
      price: "$54.99",
      image: "/logos/image2.jpg"
    },
    {
      title: "Icon Design in Adobe XD - From Sketching to Flat Icon...",
      instructor: "Caleb Kingston",
      rating: "4.5",
      reviews: "147",
      duration: "1.5 total hours",
      lectures: "36",
      level: "All Levels",
      price: "$44.99",
      image: "/logos/imagee4.jpg"
    }
  ]);
  </script>
  
  <style scoped>
  .text-purple-700 {
    color: #7c3aed;
  }
  </style>
  