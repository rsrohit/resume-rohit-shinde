<template>
  <div class="min-h-screen bg-gray-100 flex justify-center py-10 px-5">
    <div class="max-w-4xl w-full bg-white shadow-lg rounded-lg p-8">
      <header class="text-left border-b pb-6">
        <h1 class="text-4xl font-bold text-gray-900">ROHIT SHINDE</h1>
        <p class="text-lg text-gray-600 mt-2">SENIOR TEST AUTOMATION ENGINEER</p>
      </header>

      <div class="grid grid-cols-3 gap-6 mt-6">
        <!-- Left Column -->
        <div class="col-span-1 space-y-6">
          <section>
            <h2 class="text-lg font-semibold text-gray-700">CONTACTS</h2>
            <div class="mt-2 space-y-2">
              <div class="flex items-center text-gray-600">
                <i class="fas fa-map-marker-alt text-lg mr-2"></i>
                <span>Pune, Maharashtra, India</span>
              </div>
              <div class="flex items-center text-gray-600">
                <i class="fas fa-envelope text-lg mr-2"></i>
                <span>rsrohitshindeg1@gmail.com</span>
              </div>
              <div class="flex items-center text-gray-600">
                <i class="fas fa-phone-alt text-lg mr-2"></i>
                <span>+91 90 28 533 209</span>
              </div>
            </div>
          </section>

          <section>
            <h2 class="text-lg font-semibold text-gray-700">ABOUT ME</h2>
            <p class="text-gray-600 mt-2 text-sm">
              As a results-driven Automation and Manual Test Engineer, I bring over 12+ years of expertise in enhancing
              software quality through comprehensive testing strategies. My specialization spans UI automation testing,
              API automation testing, and Performance testing, leveraging tools such as Selenium WebDriver, Cypress, k6,
              TestNG, Cucumber with programming languages Java and JavaScript.
            </p>
          </section>

          <section>
            <h2 class="text-lg font-semibold text-gray-700">SKILLS</h2>
            <div class="mt-2">
              <p class="text-gray-600 text-sm">Selenium WebDriver</p>
              <p class="text-gray-600 text-sm">Cypress</p>
              <p class="text-gray-600 text-sm">Java</p>
              <p class="text-gray-600 text-sm">JavaScript</p>
              <p class="text-gray-600 text-sm">API Testing</p>
              <p class="text-gray-600 text-sm">Performance Testing</p>
              <p class="text-gray-600 text-sm">TestNG</p>
              <p class="text-gray-600 text-sm">Cucumber</p>
            </div>
          </section>

          <section>
            <h2 class="text-lg font-semibold text-gray-700">Links</h2>
            <div class="mt-2 space-y-2">
              <a href="https://linkedin.com/in/rohit-shinde-498a05a7" target="_blank"
                class="flex items-center text-gray-600 hover:text-blue-600 transition duration-300">
                <i class="fab fa-linkedin text-xl mr-2"></i>
                <span class="underline">LinkedIn</span>
              </a>
              <a href="https://github.com/rsrohit" target="_blank"
                class="flex items-center text-gray-600 hover:text-gray-900 transition duration-300">
                <i class="fab fa-github text-xl mr-2"></i>
                <span class="underline">GitHub</span>
              </a>
            </div>
          </section>
        </div>

        <!-- Right Column -->
        <div class="col-span-2">
          <section>
            <h2 class="text-lg font-semibold text-gray-700">WORK EXPERIENCE</h2>

            <div v-if="isLoading" class="flex justify-center mt-4">
              <span class="text-gray-500 text-sm">Loading experience...</span>
            </div>

            <div v-else class="mt-4 space-y-4">
              <div v-for="company in workExperience" :key="company.id">
                <h3 class="text-md font-semibold text-gray-800">{{ company.name }}</h3>
                <p class="text-sm text-gray-600 italic">{{ company.position }} ({{ company.period }})</p>
                <div v-for="project in company.projects" :key="project.project" @click="openModal(project)"
                  class="cursor-pointer p-4 border rounded-lg shadow-md hover:shadow-lg hover:bg-gray-50 transition mt-2">
                  <p class="text-sm font-semibold">{{ project.project }}</p>
                  <p class="text-xs text-gray-500">{{ project.location }}</p>
                </div>
              </div>
            </div>
          </section>
        </div>
      </div>
    </div>

    <!-- Modal for Work Experience Details -->
    <div v-if="showModal" class="fixed inset-0 flex items-center justify-center bg-gray-900 bg-opacity-50">
      <div class="bg-white w-3/4 max-w-lg rounded-lg p-6 shadow-lg max-h-[80vh] overflow-y-auto relative">
        <button @click="closeModal" class="absolute top-4 right-4 text-gray-600" aria-label="Close Modal">✖</button>
        <h2 class="text-xl font-bold text-gray-900 text-center">{{ selectedExperience.project }}</h2>
        <p class="text-gray-600 text-sm text-center">{{ selectedExperience.location }}</p>
        <div class="mt-4">
          <ul class="list-disc text-gray-600 text-sm mt-2 ml-4">
            <li v-for="point in selectedExperience.details" :key="point">{{ point }}</li>
          </ul>
          <h3 class="text-md font-semibold text-gray-800 mt-4">Skills Used</h3>
          <p class="text-gray-600 text-sm">{{ selectedExperience.skills }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import experienceData from "@/experienceData.js";

export default {
  name: "ResumePage",
  data() {
    return {
      showModal: false,
      selectedExperience: {},
      workExperience: [], // Empty initially
      isLoading: true
    };
  },
  mounted() {
    // Simulating an API request with a delay
    setTimeout(() => {
      this.workExperience = experienceData;
      this.isLoading = false;
    }, 1000);
  },
  methods: {
    openModal(company) {
      this.selectedExperience = company;
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    }
  }
};
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap');

body {
  font-family: 'Poppins', sans-serif;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>