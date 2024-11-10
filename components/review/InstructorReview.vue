<!-- components/review/InstructorReview.vue -->
<template>
    <!-- Instructor Section -->
    <div class="border p-6 rounded-lg max-w-screen-lg mx-auto mt-9 mb-8">
      <h2 class="text-xl font-bold mb-4">Instructor</h2>
      <p class="text-purple-700 font-semibold text-lg mb-1">{{ instructor.name }}</p>
      <p class="text-gray-600 text-sm">{{ instructor.title }}</p>
      <a :href="instructor.website" class="text-purple-700 hover:underline text-sm mb-4 block">{{ instructor.website }}</a>
  
      <div class="flex items-center mb-6">
        <img :src="instructor.image" alt="Instructor profile image" class="w-20 h-20 rounded-full mr-4" />
        <div class="space-y-2 text-gray-600 text-sm">
          <div class="flex items-center space-x-2"><span class="font-semibold text-gray-800">⭐ {{ instructor.rating }}</span><span>Instructor Rating</span></div>
          <div class="flex items-center space-x-2"><span>{{ instructor.reviews }} Reviews</span></div>
          <div class="flex items-center space-x-2"><span>{{ instructor.students }} Students</span></div>
          <div class="flex items-center space-x-2"><span>{{ instructor.courses }} Courses</span></div>
        </div>
      </div>
      <p class="text-gray-700 text-sm leading-relaxed">{{ instructor.description }}</p>
    </div>
  
    <!-- Course Rating and Reviews Section -->
    <div class="p-6 max-w-screen-lg mx-auto mt-9 mb-8">
      <h3 class="text-lg font-semibold mb-3">⭐ {{ courseRating.rating }} course rating • {{ courseRating.reviews }} ratings</h3>
  
      <div class="grid grid-cols-2 gap-6 mb-4">
        <div v-for="(review, index) in reviews" :key="index" class="border p-4 rounded-lg">
          <div class="flex items-center justify-between mb-2">
            <div class="flex items-center space-x-2">
              <div class="bg-black text-white rounded-full w-10 h-10 flex items-center justify-center text-sm font-bold">{{ review.initials }}</div>
              <div>
                <p class="font-semibold">{{ review.name }}</p>
                <div class="flex items-center text-sm text-black-500">
                  <span class="text-yellow-600">⭐ {{ review.rating }}</span>
                  <span class="ml-2">{{ review.date }}</span>
                </div>
              </div>
            </div>
            <button class="text-gray-500 hover:text-black">⋮</button>
          </div>
          <p class="text-gray-700 text-sm mb-3">{{ review.content }}</p>
          <div class="flex items-center space-x-2 text-gray-500 text-sm">
            <p>Helpful?</p>
            <button class="p-1 rounded-full border border-gray-300 hover:bg-gray-100 flex items-center justify-center">
              👍
            </button>
            <button class="p-1 rounded-full border border-gray-300 hover:bg-gray-100 flex items-center justify-center">
              👎
            </button>
          </div>
        </div>
      </div>
  
      <!-- Show All Reviews Button -->
      <button class="mt-4 px-6 py-2 border border-gray-400 rounded-md text-gray-600 hover:bg-gray-100">Show all reviews</button>
    </div>
  </template>
  
  <script setup>
  import { instructor, courseRating, reviews } from '@/data/instructorData';
  </script>
  
  <style scoped>
  .text-purple-700 {
    color: #7c3aed;
  }
  .leading-relaxed {
    line-height: 1.75;
  }
  </style>
  