<script>
export default {
    name: 'Footer',
    methods: {
        changeYear() {
            const currentYear = new Date().getFullYear();
            return currentYear;
        }
    },
}
</script>

<template>
  <footer class="bg-white shadow-sm dark:bg-gray-800 w-full mt-auto">
    <div class="w-full mx-auto p-4 md:flex md:items-center md:justify-between">
      <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">
        © {{ changeYear() }} <a href="/" class="hover:underline">Powered by DevApps™</a>. All Rights Reserved.
      </span>
      <ul class="flex flex-wrap items-center mt-3 text-sm font-medium text-gray-500 dark:text-gray-400 sm:mt-0">
        <li>
          <a href="https://web.facebook.com/profile.php?id=61577979652499" class="hover:underline me-4 md:me-6">Facebook</a>
        </li>
        <li>
          <a href="https://www.instagram.com/just_speakgerman?igsh=OXlqZTUyNXhtMWpy" class="hover:underline me-4 md:me-6">Instagram</a>
        </li>
      </ul>
    </div>
  </footer>
</template>