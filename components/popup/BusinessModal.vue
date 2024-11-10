<template>
  <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center z-50 bg-black bg-opacity-50">
    <div class="bg-white rounded-lg p-6 max-w-md w-full relative">
      <button @click="closeModal" class="absolute top-2 right-2 text-gray-600 text-xl">&times;</button>
      
      <!-- Modal Content -->
      <div class="text-center">
        <h2 class="text-xl font-semibold mb-3">Learn from our very best</h2>
        <p class="text-gray-700 mb-4 text-sm">
          Our Udemy Business collection is a curation of top-rated courses for individuals and organizations to upskill and reach their goals.
        </p>
        
        <img src="/logos/fresh.jpg" alt="Udemy Icon" class="mx-auto mb-4" />

        <!-- Content Sections -->
        <div class="flex flex-col items-center space-y-3 text-gray-600 text-sm">
          <div>
            <h3 class="font-semibold">Always fresh</h3>
            <p>We add to the collection based on market trends and feedback from learners and their organizations.</p>
          </div>
          <div>
            <h3 class="font-semibold">Data driven</h3>
            <p>We curate the collection based on unique data points to identify new and emerging skills.</p>
          </div>
          <div>
            <h3 class="font-semibold">Better every day</h3>
            <p>We continuously refine the collection to help learners and businesses stay one step ahead.</p>
          </div>
        </div>

        <!-- Divider Line -->
        <hr class="my-4" />

        <!-- Logo Section -->
        <div class="text-center">
          <p class="text-xs text-gray-600 mb-2 font-semibold">Trusted by organizations of all sizes</p>
          <div class="flex justify-center space-x-3 mb-3">
            <img src="/logos/nasdaq.png" alt="Nasdaq" class="h-6 grayscale" />
            <img src="/logos/volkswagen.svg" alt="Volkswagen" class="h-6 grayscale" />
            <img src="/logos/box-dark.svg" alt="Box" class="h-6 grayscale" />
            <img src="/logos/netapp-dark.svg" alt="NetApp" class="h-6 grayscale" />
            <img src="/logos/eventbrite-dark.svg" alt="Eventbrite" class="h-6 grayscale" />
          </div>
          <button class="bg-purple-600 text-white py-2 px-4 rounded-full">Try Udemy Business</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false
  }
});

const emits = defineEmits(['close']);

function closeModal() {
  emits('close');
}
</script>

<style scoped>
/* Additional styling if needed */
</style>
