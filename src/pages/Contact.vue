<script>
export default {
  name: 'Contact',
  data() {
    return {
      formData: {
        firstname: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      const emailBody = `
        Dear JustSpeak Admin,

        My name is ${this.formData.firstname} and I have the following enquiry:

        ${this.formData.message}.

        Kind regards,

        ${this.formData.firstname}

      ` ;

      const mailtoLink = `mailto:mvundomsiska13@gmail.com?subject=${encodeURIComponent(this.formData.subject)}&body=${encodeURIComponent(emailBody)}`;
      
      window.location.href = mailtoLink;
      
      // Optional: Reset form after submission
      this.formData = {
        firstname: '',
        email: '',
        subject: '',
        message: ''
      };
    }
  }
}
</script>

<template>
  <section class="bg-white dark:bg-gray-900">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
      <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-center text-gray-900 dark:text-white">Contact Us</h2>
      <p class="mb-8 lg:mb-16 font-light text-center text-gray-500 dark:text-gray-400 sm:text-xl">
        Got a question regarding learning German or German classes? Planning to write exams at a Goethe Institut? Let us know.
      </p>
      <form @submit.prevent="submitForm" class="space-y-8">
        <div>
          <label for="firstname" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Your Firstname</label>
          <input 
            v-model="formData.firstname"
            type="text" 
            id="firstname" 
            class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" 
            placeholder="Your first name" 
            required
          >
        </div>
        <div>
          <label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Your email</label>
          <input 
            v-model="formData.email"
            type="email" 
            id="email" 
            class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" 
            placeholder="name@example.com" 
            required
          >
        </div>
        <div>
          <label for="subject" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Subject</label>
          <input 
            v-model="formData.subject"
            type="text" 
            id="subject" 
            class="block p-3 w-full text-sm text-gray-900 bg-gray-50 rounded-lg border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" 
            placeholder="Let us know how we can help you" 
            required
          >
        </div>
        <div class="sm:col-span-2">
          <label for="message" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-400">Your message</label>
          <textarea 
            v-model="formData.message"
            id="message" 
            rows="6" 
            class="block p-2.5 w-full text-sm text-gray-900 bg-gray-50 rounded-lg shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" 
            placeholder="Leave a comment..."
            required
          ></textarea>
        </div>
        <button 
          type="submit" 
          class="py-3 px-5 text-sm font-medium text-center text-white rounded-lg bg-primary-700 sm:w-fit hover:bg-primary-800 focus:ring-4 focus:outline-none focus:ring-primary-300 dark:bg-primary-600 dark:hover:bg-primary-700 dark:focus:ring-primary-800"
        >
          Send message
        </button>
      </form>
    </div>
  </section>
</template>