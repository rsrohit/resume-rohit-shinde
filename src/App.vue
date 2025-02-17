<template>
  <div class="min-h-screen bg-gray-100 flex justify-center py-5 px-3 sm:py-10 sm:px-5">
    <div class="max-w-4xl w-full bg-white shadow-lg rounded-lg p-4 sm:p-8">
      <header class="text-left border-b pb-4 sm:pb-6">
        <h1 class="text-2xl sm:text-4xl font-bold text-blue-800">ROHIT SHINDE</h1>
        <p class="text-base sm:text-lg text-gray-600 mt-1 sm:mt-2">Senior Test Automation Engineer</p>
      </header>

      <!-- Grid Layout with Separator -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4 sm:gap-6 mt-4 sm:mt-6">
        <!-- Left Column -->
        <div class="col-span-1 space-y-4 sm:space-y-6 border-r border-gray-300 pr-4 sm:pr-6">
          <!-- Contacts Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-address-book mr-2"></i> Contacts
            </h2>
            <div class="mt-2 space-y-2">
              <div class="flex items-center text-sm text-gray-600">
                <i class="fas fa-map-marker-alt text-lg mr-2"></i>
                <span>Pune, Maharashtra, India</span>
              </div>
              <div class="flex items-center text-sm text-gray-600">
                <i class="fas fa-envelope text-lg mr-2"></i>
                <span>rsrohitshindeg1@gmail.com</span>
              </div>
              <div class="flex items-center text-sm text-gray-600">
                <i class="fas fa-phone-alt text-lg mr-2"></i>
                <span>+91 90 28 533 209</span>
              </div>
            </div>
          </section>

          <!-- About Me Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-user mr-2"></i> About Me
            </h2>
            <p class="text-gray-600 mt-2 text-sm">
              As a results-driven Automation and Manual Test Engineer, I bring over 12+ years of expertise in enhancing
              software quality through comprehensive testing strategies. My specialization spans UI automation testing,
              API automation testing, and Performance testing, leveraging tools such as Selenium WebDriver, Cypress, k6,
              TestNG, Cucumber with programming languages Java and JavaScript.
            </p>
          </section>

          <!-- Skills Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-tools mr-2"></i> Skills
            </h2>
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

          <!-- Education Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-graduation-cap mr-2"></i> Education
            </h2>
            <div class="mt-2">
              <h3 class="text-md font-semibold text-gray-800">Savitribai Phule Pune University</h3>
              <p class="text-sm text-gray-600">Bachelor of Computer Application, Computer Science</p>
              <p class="text-xs text-gray-500">2008 - 2011</p>
            </div>
          </section>

          <!-- Links Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-link mr-2"></i> Links
            </h2>
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
        <div class="col-span-1 md:col-span-2 pl-0 md:pl-6 mt-6 md:mt-0">
          <!-- Work Experience Section -->
          <section>
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-briefcase mr-2"></i> Work Experience
            </h2>
            <div v-if="isLoading" class="flex justify-center mt-4">
              <span class="text-gray-500 text-sm">Loading experience...</span>
            </div>
            <div v-else class="mt-4 space-y-4">
              <div v-for="company in workExperience" :key="company.id" class="relative">
                <div class="absolute -left-4 top-2 w-2 h-2 bg-blue-800 rounded-full"></div>
                <h3 class="text-md font-semibold text-indigo-600">{{ company.name }}</h3>
                <p class="text-sm text-gray-600 italic">{{ company.position }} ({{ company.period }})</p>
                <div v-for="project in company.projects" :key="project.project" @click="openModal(project)"
                  class="cursor-pointer p-4 border rounded-lg shadow-md hover:shadow-lg hover:bg-gray-50 transition mt-2">
                  <p class="text-sm font-semibold text-teal-700">{{ project.project }}</p>
                  <p class="text-xs text-gray-500">{{ project.location }}</p>
                </div>
              </div>
            </div>
          </section>

          <!-- Certification Section -->
          <section class="mt-8">
            <h2 class="text-lg font-semibold text-blue-800 flex items-center">
              <i class="fas fa-check mr-2"></i> Certification
            </h2>
            <div v-if="isLoading" class="flex justify-center mt-4">
              <span class="text-gray-500 text-sm">Loading certifications...</span>
            </div>
            <div v-else class="mt-4 space-y-4">
              <div v-for="cert in certifications" :key="cert.id" class="relative">
                <div class="absolute -left-4 top-2 w-2 h-2 bg-blue-800 rounded-full"></div>
                <div @click="openCertModal(cert)"
                  class="cursor-pointer p-4 border rounded-lg shadow-md hover:shadow-lg hover:bg-gray-50 transition">
                  <p class="text-sm font-semibold text-teal-700">{{ cert.title }}</p>
                  <p class="text-xs text-gray-500">{{ cert.platform }}</p>
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

    <!-- Modal for Certifications -->
    <div v-if="showCertModal" class="fixed inset-0 flex items-center justify-center bg-gray-900 bg-opacity-50">
      <div class="bg-white w-[800px] max-w-full rounded-lg p-6 shadow-lg max-h-[90vh] overflow-y-auto relative">
        <button @click="closeCertModal" class="absolute top-4 right-4 text-gray-600" aria-label="Close Modal">✖</button>
        <h2 class="text-xl font-bold text-gray-900 text-center">{{ selectedCert.title }}</h2>
        <p class="text-gray-600 text-sm text-center">{{ selectedCert.platform }}</p>
        <div class="mt-4 flex justify-center">
          <img :src="selectedCert.imageUrl" alt="Certification"
            class="max-w-full max-h-[70vh] border rounded-lg shadow-md">
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

      showCertModal: false,
      selectedCert: {},
      certifications: [
        {
          id: 1,
          title: "Cypress - Modern Automation Testing from Scratch + Frameworks",
          platform: "Udemy",
          imageUrl: "https://udemy-certificate.s3.amazonaws.com/image/UC-28e6db76-8a6d-403d-80ca-a46a83a6b166.jpg?v=1736420985000"
        }
      ],

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
    },

    openCertModal(cert) {
      this.selectedCert = cert;
      this.showCertModal = true;
    },
    closeCertModal() {
      this.showCertModal = false;
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