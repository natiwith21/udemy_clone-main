<!-- components/review/Students.vue -->
<template>
    <div class=" p-4 rounded-lg max-w-screen-lg mx-auto mt-9 mb-8">
        <h2 class="text-xl font-bold mb-4">Students also bought</h2>

        <!-- Courses List with conditional rendering for first 5 items -->
        <div v-for="(course, index) in visibleCourses" :key="index" class="flex items-center space-x-4 border-b py-4">
            <img :src="course.image" alt="Course image" class="w-16 h-16 rounded-md" />

            <div class="flex justify-between items-center w-full">
                <div>
                    <p class="font-semibold text-base">{{ course.title }}</p>
                    <div class="flex items-center space-x-2 text-sm text-gray-600">
                        <span v-if="course.bestseller" class="bg-green-100 text-green-700 px-1 py-0.5 rounded-full text-xs">{{ course.label }}</span>
                        <span class="text-green-800 font-semibold">{{ course.hours }} total hours</span>
                        <span>•</span>
                        <span class="text-gray-500">Updated {{ course.updated }}</span>
                    </div>
                </div>

                <div class="flex items-center space-x-4 text-sm">
                    <div class="flex items-center space-x-1">
                        <span class="text-yellow-600 font-semibold">{{ course.rating }}</span>
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor" class="text-yellow-500">
                            <path d="m14.43 10l-1.47-4.84c-.29-.95-1.63-.95-1.91 0L9.57 10H5.12c-.97 0-1.37 1.25-.58 1.81l3.64 2.6l-1.43 4.61c-.29.93.79 1.68 1.56 1.09l3.69-2.8l3.69 2.81c.77.59 1.85-.16 1.56-1.09l-1.43-4.61l3.64-2.6c.79-.57.39-1.81-.58-1.81h-4.45z"/>
                        </svg>
                    </div>

                    <div class="flex items-center space-x-1 text-gray-500">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="currentColor">
                            <path d="M7 14s-1 0-1-1s1-4 5-4s5 3 5 4s-1 1-1 1zm4-6a3 3 0 1 0 0-6a3 3 0 0 0 0 6m-5.784 6A2.24 2.24 0 0 1 5 13c0-1.355.68-2.75 1.936-3.72A6.3 6.3 0 0 0 5 9c-4 0-5 3-5 4s1 1 1 1zM4.5 8a2.5 2.5 0 1 0 0-5a2.5 2.5 0 0 0 0 5"/>
                        </svg>
                        <span>{{ course.enrolled }}</span>
                    </div>

                    <p class="font-semibold text-black">{{ course.price }}</p>

                    <button class="p-1 rounded-full border border-gray-300 hover:bg-gray-100 flex items-center justify-center">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
                            <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                        </svg>
                    </button>
                </div>
            </div>
        </div>

        <button v-if="!showAll" @click="toggleShowMore" class="mt-4 px-6 py-2 border border-gray-400 rounded-md text-gray-600 hover:bg-gray-100">
            Show more
        </button>
        <button v-else @click="toggleShowMore" class="mt-4 px-6 py-2 border border-gray-400 rounded-md text-gray-600 hover:bg-gray-100">
            Show less
        </button>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { courses } from '../data/coursesData';

const showAll = ref(false);

const visibleCourses = computed(() => {
    return showAll.value ? courses : courses.slice(0, 5);
});

const toggleShowMore = () => {
    showAll.value = !showAll.value;
};
</script>

