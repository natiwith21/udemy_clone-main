<template>
    <div class="max-w-screen-lg mx-auto mt-9 mb-8">
        <!-- Course content header -->
        <h2 class="text-xl font-bold mb-4">Course content</h2>
        <p class="text-gray-600 mb-4 flex justify-between items-center">
            <span>7 sections • 48 lectures • 3h 40m total length</span>
            <a @click.prevent="toggleAllSections" href="#" class="text-purple-600 font-semibold">
                {{ allSectionsExpanded ? "Collapse all sections" : "Expand all sections" }}
            </a>
        </p>

        <!-- Sections Accordion -->
        <div v-for="(section, index) in sections" :key="index" class="border-t border-gray-200">
            <button @click="toggleSection(index)"
                class="w-full py-3 px-4 flex justify-between items-center text-left text-lg font-semibold text-gray-800 focus:outline-none hover:bg-gray-100">
                <div class="flex items-center">
                    <!-- Arrow Icon -->
                    <span :class="activeSections.includes(index) ? 'rotate-90' : ''"
                        class="transform transition-transform mr-2">
                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                            fill="currentColor" class="text-gray-600">
                            <path d="M8 5l8 8-8 8" />
                        </svg>
                    </span>
                    <span>{{ section.title }}</span>
                </div>
                <span class="text-gray-500">{{ section.lectures.length }} lectures • {{ section.duration }}</span>
            </button>

            <transition name="fade">
                <div v-show="activeSections.includes(index)" class="pl-6 pb-4 px-4 border-t border-gray-200">
                    <ul>
                        <li v-for="(lecture, lectureIndex) in section.lectures" :key="lectureIndex"
                            class="flex justify-between items-center py-2 text-sm">
                            <div class="flex items-center space-x-2">
                                <img :src="lecture.icon" alt="icon" class="w-5 h-5" />
                                <a href="#" @click.prevent="showModal(lecture.title, lecture.videoUrl)"
                                    class="text-purple-600 hover:underline">
                                    {{ lecture.title }}
                                </a>
                            </div>
                            <div class="flex items-center space-x-2">
                                <span v-if="lecture.preview" class="text-purple-600">Preview</span>
                                <span class="text-gray-500">{{ lecture.duration }}</span>
                            </div>
                        </li>
                    </ul>
                </div>
            </transition>
        </div>

        <!-- Video Modal -->
        <VideoModal :isVisible="isModalVisible" :videoTitle="currentVideoTitle" :videoUrl="currentVideoUrl"
            @close="isModalVisible = false" />
    </div>
</template>

<script setup>
import { ref } from 'vue';
import VideoModal from './VideoModal.vue';

const sections = ref([{ title: "Introduction to the Course", duration: "2min", lectures: [{ title: "Introduction to the Course", icon: "/logos/video.png", preview: true, duration: "00:34" }, { title: "Using the Exercise Files", icon: "/logos/video.png", preview: true, duration: "01:06" }, { title: "Download Figma for Free", icon: "/logos/download.png", preview: false, duration: "00:05" }] }, { title: "Learning the Figma Interface", duration: "53min", lectures: [{ title: "Section Introduction", icon: "/logos/video.png", preview: true, duration: "00:18" }, { title: "What is Figma?", icon: "/logos/video.png", preview: true, duration: "00:48" }, { title: "Where to find Figma", icon: "/logos/video.png", preview: true, duration: "01:14" }, { title: "The Browser App vs. The Desktop App", icon: "/logos/video.png", preview: true, duration: "02:22" }, { title: "The Start Screen", icon: "/logos/video.png", preview: true, duration: "04:37" }, { title: "Introduction to the Interface", icon: "/logos/video.png", preview: true, duration: "04:30" }, { title: "Importing and Exporting Files", icon: "/logos/video.png", preview: false, duration: "02:21" }, { title: "Using Templates", icon: "/logos/video.png", preview: false, duration: "02:11" }, { title: "The Toolbar", icon: "/logos/video.png", preview: false, duration: "08:42" }, { title: "The Layers and Pages Panel", icon: "/logos/video.png", preview: false, duration: "03:20" }, { title: "The Assets Panel", icon: "/logos/video.png", preview: false, duration: "03:39" }, { title: "The Design Panel", icon: "/logos/video.png", preview: false, duration: "03:35" }] }, { title: "Setting up a new project", duration: "10min", lectures: [{ title: "Creating a New Project and File", icon: "/logos/video.png", preview: false, duration: "01:38" }, { title: "Importing Sketch Files", icon: "/logos/video.png", preview: false, duration: "02:45" }, { title: "Working with Teams", icon: "/logos/video.png", preview: false, duration: "03:41" }, { title: "Working with Templates", icon: "/logos/video.png", preview: false, duration: "01:44" }] }, { title: "Adding and Editing Content", duration: "1hr 44min", lectures: [{ title: "Working with Frames", icon: "/logos/video.png", preview: false, duration: "06:05" }, { title: "Working with Shapes", icon: "/logos/video.png", preview: false, duration: "17:58" }, { title: "Drawing Icons using the Pen Tool", icon: "/logos/video.png", preview: false, duration: "07:47" }, { title: "Drawing Shapes Using the Pencil Tool", icon: "/logos/video.png", preview: false, duration: "03:43" }, { title: "Working with Text", icon: "/logos/video.png", preview: false, duration: "07:33" }, { title: "Masking Images and Shapes", icon: "/logos/video.png", preview: false, duration: "06:38" }, { title: "Importing Icons and other Graphics", icon: "/logos/video.png", preview: false, duration: "07:45" }, { title: "Working with Color", icon: "/logos/video.png", preview: false, duration: "06:27" }, { title: "Working with Styles", icon: "/logos/video.png", preview: false, duration: "06:13" }, { title: "Setting up Components", icon: "/logos/video.png", preview: false, duration: "20:50" }, { title: "Using Constraints for Responsive Design", icon: "/logos/video.png", preview: false, duration: "10:29" }, { title: "Working with Version Control", icon: "/logos/video.png", preview: false, duration: "02:04" }] }, { title: "Completing the Design", duration: "37min", lectures: [{ title: "Designing a Slide-out Menu", icon: "/logos/video.png", preview: false, duration: "03:53" }, { title: "Designing an on-screen Overlay", icon: "/logos/video.png", preview: false, duration: "11:48" }, { title: "Designing a comments section", icon: "/logos/video.png", preview: false, duration: "12:28" }, { title: "Designing Multiple Artboard States", icon: "/logos/video.png", preview: false, duration: "05:16" }, { title: "Give this design its own unique personality", icon: "/logos/video.png", preview: false, duration: "03:19" }] }, { title: "Prototyping, Sharing, and Exporting", duration: "15min", lectures: [{ title: "Creating a prototype", icon: "/logos/video.png", preview: false, duration: "06:45" }, { title: "Viewing your prototype on a mobile device", icon: "/logos/video.png", preview: false, duration: "00:43" }, { title: "Live device preview", icon: "/logos/video.png", preview: false, duration: "01:11" }, { title: "Sharing your design", icon: "/logos/video.png", preview: false, duration: "01:18" }, { title: "Allowing others to comment on your design", icon: "/logos/video.png", preview: false, duration: "01:16" }, { title: "Exporting graphics and assets", icon: "/logos/video.png", preview: false, duration: "04:04" }] }, { title: "Conclusion", duration: "1min", lectures: [{ title: "Course Wrap-up", icon: "/logos/video.png", preview: false, duration: "01:00" }] }]);

const activeSections = ref([]);
const allSectionsExpanded = ref(false);
const isModalVisible = ref(false);
const currentVideoTitle = ref('');
const currentVideoUrl = ref('');

// Function to toggle individual sections
function toggleSection(index) {
    if (activeSections.value.includes(index)) {
        activeSections.value = activeSections.value.filter(i => i !== index);
    } else {
        activeSections.value.push(index);
    }
}

// Function to toggle all sections
function toggleAllSections() {
    if (allSectionsExpanded.value) {
        activeSections.value = [];
    } else {
        activeSections.value = sections.value.map((_, index) => index);
    }
    allSectionsExpanded.value = !allSectionsExpanded.value;
}

// Function to show modal with video details
function showModal(title, url) {
    currentVideoTitle.value = title;
    currentVideoUrl.value = url;
    isModalVisible.value = true;
}
</script>

<style scoped>
/* Fade transition for expanding and collapsing sections */
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>