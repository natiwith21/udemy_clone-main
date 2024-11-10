<!-- components/FeaturedReview.vue -->
<template>
    <div class="border p-6 rounded-lg max-w-screen-lg mx-auto mt-9 mb-8">
      <h2 class="text-xl font-bold mb-4">Featured review</h2>
  
      <!-- Reviewer Info -->
      <div class="flex items-center mb-4">
        <img src="/logos/review.jpg" alt="Reviewer profile" class="w-16 h-16 rounded-full mr-4" />
        <div>
          <p class="font-semibold">Thomas R.</p>
          <p class="text-gray-500 text-sm">8 courses • 1 review</p>
        </div>
      </div>
  
      <!-- Rating and Review -->
      <div class="flex items-center mb-2">
        <RatingIcon />
        <p class="text-gray-500 text-sm ml-2">4 years ago</p>
      </div>
      <p class="text-gray-700 mb-4">
        A good and clear course! The reason I don't rate it five stars is because I wish there were even more neat tips and tricks / shortcuts that a more experienced user could learn from. In this case it would also be nice to see some "edge cases" of the use of this app, and how to maneuver this in an elegant way. But all in all a good and concise Figma course!
      </p>
  
      <!-- Helpful Vote and Report -->
      <div class="flex items-center space-x-4">
        <p class="text-gray-600">Was this review helpful?</p>
        
        <!-- Thumbs Up Button -->
        <button class="p-2 rounded-full border border-gray-300 hover:bg-gray-100 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M5 9v12H1V9zm4 12a2 2 0 0 1-2-2V9c0-.55.22-1.05.59-1.41L14.17 1l1.06 1.06c.27.27.44.64.44 1.05l-.03.32L14.69 8H21a2 2 0 0 1 2 2v2c0 .26-.05.5-.14.73l-3.02 7.05C19.54 20.5 18.83 21 18 21zm0-2h9.03L21 12v-2h-8.79l1.13-5.32L9 9.03z"/>
          </svg>
        </button>
  
        <!-- Thumbs Down Button -->
        <button class="p-2 rounded-full border border-gray-300 hover:bg-gray-100 flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M19 15V3h4v12zM15 3a2 2 0 0 1 2 2v10c0 .55-.22 1.05-.59 1.41L9.83 23l-1.06-1.06c-.27-.27-.44-.64-.44-1.06l.03-.31l.95-4.57H3a2 2 0 0 1-2-2v-2c0-.26.05-.5.14-.73l3.02-7.05C4.46 3.5 5.17 3 6 3zm0 2H5.97L3 12v2h8.78l-1.13 5.32L15 14.97z"/>
          </svg>
        </button>
  
        <a href="#" class="text-gray-600 hover:text-black underline ml-4">Report</a>
      </div>
    </div>
  </template>
  
  <script setup>
  // No additional logic needed for this static component
  </script>
  
  <style scoped>
  .material-icons {
    font-size: 1.2rem;
  }
  button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
  }
  </style>
  