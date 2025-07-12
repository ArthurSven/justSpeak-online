<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuOpen: false,
      navItems: [
        { name: 'Home', path: '/' },
        { name: 'About', path: '/about' },
        { name: 'Contact', path: '/contact' }
      ],
       appLink: 'https://play.google.com/store/apps/details?id=com.devapps.justspeak_20'
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    }
  }
}
</script>

<template>
  <nav class=" border-gray-200 dark:bg-gray-900">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
      <a href="/" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img src="../assets/images/justspeaklogo.png" class="h-8" alt="Website Logo" />
        <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">JustSpeak</span>
      </a>
      
      <!-- Mobile menu button -->
      <button 
        @click="toggleMenu"
        type="button" 
        class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" 
        aria-controls="navbar-default" 
        :aria-expanded="isMenuOpen"
      >
        <span class="sr-only">Open main menu</span>
        <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
        </svg>
      </button>

      <div class="flex items-center md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
        <!-- Download App Button - Desktop -->
        <a 
          :href="appLink" 
          target="_blank"
          class="hidden md:flex items-center justify-center px-4 py-2 text-sm font-medium text-white bg-blue-700 rounded-lg hover:bg-blue-700 focus:ring-4 focus:ring-blue-700 dark:bg-blue-700 dark:hover:bg-blue-700 dark:focus:ring-blue-900"
        >
          <svg class="w-4 h-4 me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 18 20">
            <path d="M17.9 8.18a3 3 0 0 0-.1-.82 2.6 2.6 0 0 0-.2-.78 3.2 3.2 0 0 0-.5-.72A2.6 2.6 0 0 0 16 5.6a3 3 0 0 0-2-.8H4a3 3 0 0 0-2 .8 2.6 2.6 0 0 0-.5.72 3.2 3.2 0 0 0-.2.78 3 3 0 0 0-.1.82v2.72a41 41 0 0 0 4.5 3.1 8.4 8.4 0 0 0 2 1.1 5 5 0 0 0 1.7.2 5 5 0 0 0 1.7-.2 8.4 8.4 0 0 0 2-1.1 41 41 0 0 0 4.5-3.1V8.18Zm-7 6.64a3 3 0 0 1-1.4.4 3 3 0 0 1-1.4-.4 41.4 41.4 0 0 1-4.3-3V15a1 1 0 0 0 1 1h10a1 1 0 0 0 1-1v-2.2a41.4 41.4 0 0 1-4.3 3Z"/>
            <path d="M6.5 10.5a1 1 0 1 0 0-2 1 1 0 0 0 0 2Zm5 0a1 1 0 1 0 0-2 1 1 0 0 0 0 2Z"/>
          </svg>
          Download App
        </a>
        
        <!-- Mobile menu button -->
        <button 
          @click="toggleMenu"
          type="button" 
          class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" 
          aria-controls="navbar-default" 
          :aria-expanded="isMenuOpen"
        >
          <span class="sr-only">Open main menu</span>
          <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
          </svg>
        </button>
      </div>
      
      <!-- Navigation links -->
      <div 
        :class="{'hidden': !isMenuOpen, 'block': isMenuOpen}" 
        class="w-full md:block md:w-auto" 
        id="navbar-default"
      >
      <ul class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
      <li v-for="item in navItems" :key="item.path">
        <router-link 
          :to="item.path" 
          class="block py-2 px-3 text-gray-900 rounded-sm hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
          active-class="text-white bg-blue-700 md:bg-transparent md:text-blue-700 md:dark:text-blue-500"
        >
          {{ item.name }}
        </router-link>
      </li>
    </ul>
      </div>
    </div>
  </nav>
</template>