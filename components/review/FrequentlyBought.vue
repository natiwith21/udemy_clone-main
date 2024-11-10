<!-- components/FrequentlyBoughtTogether.vue -->
<template>
    <div class="border p-4 rounded-lg max-w-screen-lg mx-auto mt-9 mb-8">
      <h2 class="text-xl font-bold mb-4">Frequently Bought Together</h2>
  
      <!-- Courses List with increased height for each item -->
      <div v-for="(course, index) in courses" :key="index" class="flex items-center space-x-4 border-b py-8">
        <!-- Course Image -->
        <img :src="course.image" alt="Course image" class="w-24 h-24 rounded-md" />
  
        <!-- Main Content with Title, Rating, Instructor, and Price -->
        <div class="flex justify-between items-center w-full">
          <div>
            <p class="font-semibold text-lg">{{ course.title }}</p>
            <p class="text-gray-500 text-sm">{{ course.instructor }}</p>
            <div class="flex items-center space-x-1 text-sm">
              <span class="text-yellow-600 font-semibold">{{ course.rating }}</span>
              <span v-for="i in Math.floor(course.rating)" :key="i" class="text-yellow-500">★</span>
              <span class="text-gray-500">({{ course.enrolled }})</span>
            </div>
            <span v-if="course.bestseller" class="bg-yellow-100 text-yellow-700 px-1 py-0.5 rounded-full text-xs">Bestseller</span>
          </div>
  
          <!-- Price -->
          <p class="font-semibold text-black text-lg">{{ course.price }}</p>
        </div>
      </div>
  
      <!-- Total and Go to Cart Button -->
      <div class="flex justify-between items-center mt-4">
        <p class="font-semibold text-lg">Total: <span class="text-purple-600">{{ total }}</span></p>
        <button class="px-6 py-2 bg-purple-600 text-white rounded-md hover:bg-purple-700">
          Go to cart
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const courses = [
    {
      title: "Learn Figma - UI/UX Design Essential Training",
      image: "/logos/teacher.jpg",
      instructor: "Caleb Kingston",
      rating: "4.4",
      enrolled: "16,950",
      price: "$54.99",
    },
    {
      title: "DESIGN RULES: Principles + Practices for Great UI Design",
      image: "/logos/joe-2.jpg",
      instructor: "Joe Natoli",
      rating: "4.6",
      enrolled: "14,481",
      price: "$69.99",
      bestseller: true,
    },
    {
      title: "UX & Web Design Master Course: Strategy, Design, Development",
      image: "/logos/joe.jpg",
      instructor: "Joe Natoli",
      rating: "4.6",
      enrolled: "15,393",
      price: "$64.99",
    }
  ];
  
  const total = ref('$189.97');
  </script>
  
  <style scoped>
  /* Increase padding to give each item a larger, more spacious feel */
  .border-b {
    padding-top: 2rem;
    padding-bottom: 2rem;
  }
  
  .w-24 {
    width: 6rem;
    height: 6rem;
  }
  
  button {
    transition: background-color 0.3s ease;
  }
  </style>
  