<!-- components/StickyHeader.vue -->
<template>
    <div v-if="showStickyHeader" class="sticky-header">
      <div class="sticky-header-content">
        <p class="text-lg font-semibold">Learn Figma - UI/UX Design Essential Training</p>
        <div class="flex items-center space-x-2 text-gray-400 text-sm">
          <span class="text-yellow-500">⭐ {{ course.rating }}</span>
          <a href="#" class="text-blue-600 underline">{{ course.ratingsCount }} ratings</a>
          <span>{{ course.studentsCount }} students</span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from "vue";
  
  // Course data for the sticky header
  const course = {
    rating: "4.4",
    ratingsCount: "16,954",
    studentsCount: "66,765",
  };
  
  // State to control the visibility of the sticky header
  const showStickyHeader = ref(false);
  
  // Function to handle scroll and toggle the sticky header visibility
  const handleScroll = () => {
    showStickyHeader.value = window.scrollY > 100;
  };
  
  // Register scroll event on mount and remove it on unmount
  onMounted(() => {
    window.addEventListener("scroll", handleScroll);
  });
  
  onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
  });
  </script>
  
  <style scoped>
  /* Sticky Header Styling */
  .sticky-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: #1e1e1e;
    color: white;
    padding: 12px 20px;
    display: flex;
    align-items: center;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
    z-index: 1000;
  }
  
  .sticky-header-content {
    display: flex;
    flex-direction: column;
  }
  </style>
  