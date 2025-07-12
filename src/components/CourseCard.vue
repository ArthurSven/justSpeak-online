<script setup>

const courses = [
  {
    title: "A1 German",
    level: "Lower Beginner",
    description: "Start speaking basic German in just 4 weeks. Learn essential vocabulary and grammar through practical conversation exercises.",
    duration: "8 weeks",
    price: "$199",
    levelColor: "green",
    icon: "M17 11h-2.722L8 17.278a5.512 5.512 0 0 1-.9.722H17a1 1 0 0 0 1-1v-5a1 1 0 0 0-1-1ZM6 0H1a1 1 0 0 0-1 1v13.5a3.5 3.5 0 1 0 7 0V1a1 1 0 0 0-1-1ZM3.5 15.5a1 1 0 1 1 0-2 1 1 0 0 1 0 2ZM16.132 4.9 12.6 1.368a1 1 0 0 0-1.414 0L9 3.55v9.9l7.132-7.132a1 1 0 0 0 0-1.418Z"
  },
  {
    title: "A2 German",
    level: "Upper Beginner",
    description: "Build on your basics with more complex conversations. Master present, past and future tenses for everyday communication.",
    duration: "10 weeks",
    price: "$249",
    levelColor: "blue",
    icon: "M17 11h-2.722L8 17.278a5.512 5.512 0 0 1-.9.722H17a1 1 0 0 0 1-1v-5a1 1 0 0 0-1-1ZM6 0H1a1 1 0 0 0-1 1v13.5a3.5 3.5 0 1 0 7 0V1a1 1 0 0 0-1-1ZM3.5 15.5a1 1 0 1 1 0-2 1 1 0 0 1 0 2ZM16.132 4.9 12.6 1.368a1 1 0 0 0-1.414 0L9 3.55v9.9l7.132-7.132a1 1 0 0 0 0-1.418Z"
  },
  {
    title: "B1 German",
    level: "Intermediate",
    description: "Achieve conversational fluency. Discuss complex topics, understand native speakers, and prepare for Goethe-Zertifikat B1.",
    duration: "12 weeks",
    price: "$299",
    levelColor: "purple",
    icon: "M5 4 1 8l4 4m10-8 4 4-4 4M11 1 9 15"
  }
]

const sendEmail = (courseTitle) => {
  const subject = `Enquiry about ${courseTitle}`
  window.location.href = `mailto:mvundomsiska@gmail.com?subject=${encodeURIComponent(subject)}`
}
</script>

<template>
  <div class="grid md:grid-cols-3 gap-8">
    <div 
      v-for="course in courses" 
      :key="course.title"
      class="bg-gray-50 dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-lg p-8 md:p-12"
    >
      <span 
        class="text-xs font-medium inline-flex items-center px-2.5 py-0.5 rounded-md mb-2"
        :class="{
          'bg-green-100 text-green-800 dark:bg-gray-700 dark:text-green-400': course.levelColor === 'green',
          'bg-blue-100 text-blue-800 dark:bg-blue-900 dark:text-blue-400': course.levelColor === 'blue',
          'bg-purple-100 text-purple-800 dark:bg-purple-900 dark:text-purple-400': course.levelColor === 'purple'
        }"
      >
        <svg 
          class="w-2.5 h-2.5 me-1.5" 
          aria-hidden="true" 
          xmlns="http://www.w3.org/2000/svg" 
          fill="currentColor" 
          viewBox="0 0 18 18"
          v-if="course.levelColor !== 'purple'"
        >
          <path :d="course.icon"/>
        </svg>
        <svg 
          class="w-2.5 h-2.5 me-1.5" 
          aria-hidden="true" 
          xmlns="http://www.w3.org/2000/svg" 
          fill="none" 
          viewBox="0 0 20 16"
          v-else
        >
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" :d="course.icon"/>
        </svg>
        {{ course.level }}
      </span>
      
      <h2 class="text-gray-900 dark:text-white text-3xl font-extrabold mb-2">{{ course.title }}</h2>
      
      <p class="text-lg font-normal text-gray-500 dark:text-gray-400 mb-4">
        {{ course.description }}
      </p>
      
      <div class="flex justify-between items-center mb-6">
        <span class="text-gray-700 dark:text-gray-300 font-medium">
          ⏳ {{ course.duration }}
        </span>
        <span class="text-gray-900 dark:text-white font-bold">
          {{ course.price }}
        </span>
      </div>
      
      <button 
        @click="sendEmail(course.title)"
        class="w-full inline-flex justify-center items-center py-2.5 px-5 text-base font-medium text-center text-white rounded-lg bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-900"
      >
        Enquire Now
        <svg class="w-3.5 h-3.5 ms-2 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
        </svg>
      </button>
    </div>
  </div>
</template>