<!-- components/CourseHeader.vue -->
<template>
    <div class="bg-gray-900 text-white py-8 w-full">
        <div class="max-w-screen-lg mx-auto px-6">
            <!-- Breadcrumb -->
            <div class="text-sm text-gray-400 mb-2">
                <span class="hover:underline cursor-pointer">Design</span>
                <span> &gt; </span>
                <span class="hover:underline cursor-pointer">User Experience Design</span>
                <span> &gt; </span>
                <span class="hover:underline cursor-pointer">Figma</span>
            </div>

            <!-- Course Title -->
            <h1 class="text-3xl font-bold mb-2">Learn Figma - UI/UX Design Essential Training</h1>

            <!-- Course Description -->
            <p class="text-lg text-gray-300 mb-4">
                Learn how to design a beautiful and engaging mobile app with Figma. Learn-by-doing approach.
            </p>

            <!-- Rating and Students -->
            <div class="flex items-center space-x-2 text-yellow-400 mb-2">
                <span class="text-xl font-semibold">4.4</span>
                <RatingIcon />
                <span class="text-sm text-gray-400">(16,954 ratings)</span>
                <span class="text-sm text-gray-400">66,764 students</span>
            </div>

            <!-- Creator Information -->
            <p class="text-sm text-gray-400 mb-4">
                Created by <span class="text-blue-400 hover:underline cursor-pointer">Caleb Kingston</span>
            </p>

            <!-- Additional Info -->
            <div class="flex items-center space-x-4 text-sm text-gray-400">
                <div class="flex items-center space-x-1">
                    <CalendarIcon />
                    <span>Last updated 6/2023</span>
                </div>

                <div class="flex items-center space-x-1">
                    <LanguageIcon />
                    <span>English</span>
                </div>

                <div class="flex items-center space-x-1">
                    <SubtitlesIcon />
                    <span>English [Auto], Arabic [Auto], 13 more</span>
                </div>
            </div>
        </div>
    </div>
    <FixedCard />
</template>

<script setup>
import CalendarIcon from '~/components/icons/CalendarIcon.vue';
import LanguageIcon from '~/components/icons/LanguageIcon.vue';
import SubtitlesIcon from '~/components/icons/SubtitlesIcon.vue';
</script>

<style scoped>
/* Additional styles if needed */
</style>
