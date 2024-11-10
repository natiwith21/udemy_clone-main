<!-- components/SidebarCourseCard.vue -->
<template>
    <div class="fixed right-4 top-20 w-80 bg-white shadow-lg rounded-lg p-4">
      <!-- Sidebar content goes here -->
      <div class="relative">
        <img src="https://via.placeholder.com/320x180" alt="Course preview" class="rounded-t-lg w-full" />
        <!-- Play button overlay -->
        <button class="absolute inset-0 flex items-center justify-center">
          <div class="bg-black bg-opacity-50 p-3 rounded-full">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="white" viewBox="0 0 24 24">
              <path d="M8 5v14l11-7z" />
            </svg>
          </div>
        </button>
        <p class="absolute bottom-2 left-2 text-white font-semibold">Preview this course</p>
      </div>
  
      <!-- Subscription Information -->
      <div class="mt-4">
        <p class="font-semibold">Subscribe to Udemy’s top courses</p>
        <p class="text-gray-600 text-sm mb-4">
          Get this course, plus 12,000+ of our top-rated courses, with Personal Plan.
          <a href="#" class="text-purple-600 font-semibold">Learn more</a>
        </p>
  
        <!-- Try Personal Plan Button -->
        <button class="w-full py-2 text-white bg-purple-600 rounded font-semibold mb-2">Try Personal Plan for free</button>
        <p class="text-center text-gray-500 text-sm">Starting at $10.00 per month after trial<br />Cancel anytime</p>
      </div>
  
      <hr class="my-4" />
  
      <!-- One-time Purchase Price -->
      <div class="text-center">
        <p class="text-2xl font-bold">$54.99</p>
        <button class="w-full py-2 mt-2 border border-gray-700 rounded font-semibold">Add to cart</button>
        <p class="text-sm text-gray-500 mt-2">30-Day Money-Back Guarantee<br />Full Lifetime Access</p>
      </div>
  
      <hr class="my-4" />
  
      <!-- Additional Links -->
      <div class="flex justify-around text-sm text-gray-600 font-semibold">
        <a href="#" class="hover:underline">Share</a>
        <a href="#" class="hover:underline">Gift this course</a>
        <a href="#" class="hover:underline">Apply Coupon</a>
      </div>
    </div>
  </template>
  
  <script setup>
  // No additional logic needed at this time.
  </script>
  
  <style scoped>
  /* Additional styling if necessary */
  </style>
  