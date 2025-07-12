<script>
export default {
  name: 'Home',
  data() {
    return {
      courses: [
        {
          title: "A1 German",
          level: "Lower Beginner",
          description: "Start speaking basic German in just 4 weeks. Learn essential vocabulary and grammar through practical conversation exercises.",
          duration: "3 Months",
          price: "MWK 90,000",
          levelColor: "green",
          icon: "M17 11h-2.722L8 17.278a5.512 5.512 0 0 1-.9.722H17a1 1 0 0 0 1-1v-5a1 1 0 0 0-1-1ZM6 0H1a1 1 0 0 0-1 1v13.5a3.5 3.5 0 1 0 7 0V1a1 1 0 0 0-1-1ZM3.5 15.5a1 1 0 1 1 0-2 1 1 0 0 1 0 2ZM16.132 4.9 12.6 1.368a1 1 0 0 0-1.414 0L9 3.55v9.9l7.132-7.132a1 1 0 0 0 0-1.418Z"
        },
        {
          title: "A2 German",
          level: "Upper Beginner",
          description: "Build on your basics with more complex conversations. Master present, past and future tenses for everyday communication.",
          duration: "3 Months",
          price: "NWK 110,000",
          levelColor: "blue",
          icon: "M17 11h-2.722L8 17.278a5.512 5.512 0 0 1-.9.722H17a1 1 0 0 0 1-1v-5a1 1 0 0 0-1-1ZM6 0H1a1 1 0 0 0-1 1v13.5a3.5 3.5 0 1 0 7 0V1a1 1 0 0 0-1-1ZM3.5 15.5a1 1 0 1 1 0-2 1 1 0 0 1 0 2ZM16.132 4.9 12.6 1.368a1 1 0 0 0-1.414 0L9 3.55v9.9l7.132-7.132a1 1 0 0 0 0-1.418Z"
        },
        {
          title: "B1 German",
          level: "Intermediate",
          description: "Achieve conversational fluency. Discuss complex topics, understand native speakers, and prepare for Goethe-Zertifikat B1.",
          duration: "3 Months",
          price: "MWK 120,000",
          levelColor: "purple",
          icon: "M5 4 1 8l4 4m10-8 4 4-4 4M11 1 9 15"
        }
      ]
    }
  },
  methods: {
    sendEmail(courseTitle) {
      const subject = `Enquiry about ${courseTitle}`
      window.location.href = `mailto:mvundomsiska@gmail.com?subject=${encodeURIComponent(subject)}`
    }
  }
}
</script>

<template>
  

<section class="bg-white">
    <div class="py-8 px-4 mx-auto max-w-screen-xl lg:py-16">
        <div class="bg-gray-5 border border-gray-200 rounded-lg p-8 md:p-12 mb-8">
            
            <h1 class="text-gray-900 text-3xl md:text-5xl font-extrabold mb-2">JustSpeak German</h1>
            <p class="text-lg font-normal text-gray-500 mb-4 mt-4">
    Our mission at JustSpeak is simple: get you speaking <span class="font-semibold text-gray-700">real, practical German</span> from your very first lesson. 
  </p>
  <p class="text-lg font-normal text-gray-500 = mb-4">
    Unlike traditional language schools, we combine <span class="font-semibold text-gray-700">Goethe Institute standards</span> with <span class="font-semibold text-gray-700">conversation-focused teaching</span>, ensuring you not only pass exams but actually communicate with confidence.
  </p>
  <p class="text-lg font-normal text-gray-500 dark:text-gray-400 mb-6">
    We make quality German education accessible with <span class="font-semibold text-gray-700">affordable group classes</span> and <span class="font-semibold text-gray-700">personalized coaching</span>, cutting through the grammar-heavy approach to get you speaking faster.
  </p>
        </div>
        <!--course card below-->
  <div class="grid md:grid-cols-3 gap-8 mt-12">
                <div 
                    v-for="course in courses" 
                    :key="course.title"
                    class="bg-gray-900 border border-gray-200 rounded-lg p-8 md:p-12"
                >
                    <span 
                        class="text-xs font-medium inline-flex items-center px-2.5 py-0.5 rounded-md mb-2"
                        :class="{
                            'bg-green-100 text-green-800': course.levelColor === 'green',
                            'bg-blue-100 text-blue-800': course.levelColor === 'blue',
                            'bg-purple-100 text-purple-800': course.levelColor === 'purple'
                        }"
                    >
                        <svg 
                            class="w-2.5 h-2.5 me-1.5" 
                            aria-hidden="true" 
                            xmlns="http://www.w3.org/2000/svg" 
                            :fill="course.levelColor === 'purple' ? 'none' : 'currentColor'" 
                            :viewBox="course.levelColor === 'purple' ? '0 0 20 16' : '0 0 18 18'"
                            :stroke="course.levelColor === 'purple' ? 'currentColor' : ''"
                        >
                            <path :stroke-width="course.levelColor === 'purple' ? '2' : ''" :d="course.icon"/>
                        </svg>
                        {{ course.level }}
                    </span>
                    
                    <h2 class="text-white text-3xl font-extrabold mb-2">{{ course.title }}</h2>
                    
                    <p class="text-lg font-normal text-gray-500 mb-4">
                        {{ course.description }}
                    </p>
                    
                    <div class="flex justify-between items-center mb-6">
                        <span class="text-white font-medium">
                            ⏳ {{ course.duration }}
                        </span>
                        <span class="text-gray-900 font-bold">
                            {{ course.price }}
                        </span>
                    </div>
                    
                    <button 
                        @click="sendEmail(course.title)"
                        class="w-full inline-flex justify-center items-center py-2.5 px-5 text-base font-medium text-center text-white rounded-lg bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300"
                    >
                        Enquire Now
                        <svg class="w-3.5 h-3.5 ms-2 rtl:rotate-180" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                        </svg>
                    </button>
                </div>
            </div>
  <!--course cards end-->
    </div>
</section>

</template>