<template>
  <div class="font-sans bg-gray-100">
    <!-- Header Section -->
    <header class="bg-blue-600 text-white py-6 text-center">
      <h1 class="text-4xl font-bold">Rohit Shinde</h1>
      <p class="text-xl">Senior Test Automation Engineer</p>
    </header>

    <!-- About Me Section -->
    <section class="container mx-auto px-4 py-8">
      <h2 class="text-2xl font-bold text-blue-600 mb-4">About Me</h2>
      <p class="text-gray-700">
        As a results-driven Automation and Manual Test Engineer, I bring over 12 years of expertise in enhancing software quality through comprehensive testing strategies. My specialization spans web automation, API testing, and performance testing, leveraging tools such as Selenium WebDriver, Cypress, Java, JavaScript, TestNG, and Cucumber.
      </p>
    </section>

    <!-- Work Experience Section -->
    <section class="container mx-auto px-4 py-8">
      <h2 class="text-2xl font-bold text-blue-600 mb-4">Work Experience</h2>
      <div class="bg-white shadow-md rounded-lg p-6 mb-6">
        <h3 class="text-xl font-semibold">Senior Test Automation Engineer</h3>
        <p class="text-gray-600"><strong>Globant, Pune</strong> | DEC 2020 - Present</p>
        <ul class="list-disc list-inside mt-4">
          <li>Collaborated with the Partner Travel team to ensure the quality of applications designed for customers of financial institutions like FIS and Mastercard.</li>
          <li>Utilized WebdriverIO with JavaScript for automation testing and employed JIRA with the Xray plugin for manual test case development and execution.</li>
        </ul>
      </div>
      <!-- Add more job entries here -->
    </section>

    <!-- Skills Section -->
    <section class="container mx-auto px-4 py-8">
      <h2 class="text-2xl font-bold text-blue-600 mb-4">Skills</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div class="bg-white shadow-md rounded-lg p-6">
          <h3 class="text-lg font-semibold">Web Automation Testing</h3>
        </div>
        <div class="bg-white shadow-md rounded-lg p-6">
          <h3 class="text-lg font-semibold">API Testing</h3>
        </div>
        <div class="bg-white shadow-md rounded-lg p-6">
          <h3 class="text-lg font-semibold">Selenium WebDriver</h3>
        </div>
        <!-- Add more skills here -->
      </div>
    </section>

    <!-- Education Section -->
    <section class="container mx-auto px-4 py-8">
      <h2 class="text-2xl font-bold text-blue-600 mb-4">Education</h2>
      <div class="bg-white shadow-md rounded-lg p-6">
        <p class="text-gray-700"><strong>Bachelor of Computer Application</strong> | Savitribai Phule Pune University</p>
      </div>
    </section>

    <!-- Links Section -->
    <section class="container mx-auto px-4 py-8">
      <h2 class="text-2xl font-bold text-blue-600 mb-4">Links</h2>
      <div class="flex space-x-4">
        <a href="https://linkedin.com/in/rohit-shinde-498a05a7" target="_blank" class="text-blue-600 hover:underline">
          <i class="fab fa-linkedin"></i> LinkedIn
        </a>
        <a href="https://github.com/rsrohit" target="_blank" class="text-blue-600 hover:underline">
          <i class="fab fa-github"></i> GitHub
        </a>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
/* Add custom styles if needed */
</style>