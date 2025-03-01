<script setup>
import { ref } from 'vue';
// Using direct URL imports for SVG files
const backgroundImage = '/background.svg';
const cardImage = '/card-group.svg';
const mobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value;
};
</script>

<template>
  <div class="min-h-screen bg-white" >
    <!-- Navigation -->
    <nav class="px-5 md:px-16 py-[22px] flex justify-between items-center">
      <img src="/finteca.svg" alt="Finteca Logo" class="h-8">
      
      <!-- Desktop Navigation -->
      <div class="hidden lg:flex space-x-6">
        <a href="#" class="text-gray-600 hover:text-gray-900">Home</a>
        <a href="#" class="text-gray-600 hover:text-gray-900">For Businesses</a>
        <a href="#" class="text-gray-600 hover:text-gray-900">For Agent</a>
        <a href="#" class="text-gray-600 hover:text-gray-900">For Customers</a>
        <a href="#" class="text-gray-600 hover:text-gray-900">Documentation</a>
        <a href="#" class="text-gray-600 hover:text-gray-900">Support</a>
      </div>
      
      <!-- Medium Screen Navigation -->
      <div class="hidden md:flex lg:hidden space-x-3">
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Home</a>
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Business</a>
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Agent</a>
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Customers</a>
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Docs</a>
        <a href="#" class="text-gray-600 hover:text-gray-900 text-sm">Support</a>
      </div>
      
      <!-- Mobile Menu Button -->
      <button @click="toggleMobileMenu" class="md:hidden text-gray-600 hover:text-gray-900">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
      <div class="hidden md:block">
        <button class="bg-black text-white px-4 py-2 rounded-[48px] hover:bg-gray-800">Get Started</button>
      </div>
    </nav>

    <!-- Mobile Menu Overlay -->
    <div v-if="mobileMenuOpen" class="fixed inset-0 z-50">
      <!-- Dimmed Background -->
      <div class="absolute inset-0 bg-black/50"></div>
      
      <!-- Menu Panel -->
      <div class="absolute top-0 left-0 right-0 bg-white rounded-b-lg shadow-lg p-6">
        <div class="flex justify-between items-center mb-8">
          <div class="text-[#28A066] font-bold text-2xl">Finteca</div>
          <button @click="toggleMobileMenu" class="text-gray-600">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
        <div class="flex flex-col space-y-6">
          <a href="#" class="text-gray-800 text-base">Home</a>
          <a href="#" class="text-gray-800 text-base">For Businesses</a>
          <a href="#" class="text-gray-800 text-base">For Agent</a>
          <a href="#" class="text-gray-800 text-base">For Customers</a>
          <a href="#" class="text-gray-800 text-base">Documentation</a>
          <a href="#" class="text-gray-800 text-base">Support</a>
          <div class="pt-4 flex justify-center">
            <button class="bg-black text-white px-6 py-3 rounded-[48px] ">Get Started</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Hero Section -->
    <div class="container mx-auto px-4 py-4 md:py-8 flex flex-col md:flex-row items-center pb-24 md:pb-4">
      <!-- Left Content -->
      <div class="md:w-1/2 md:mb-0 text-center md:text-left ">
        <h1 class="title text-[7vw] sm:text-[6vw] md:text-[5vw] lg:text-[54.35px] mb-2">
          Your Crypto, Your Card,<br />
          Your Control
        </h1>
        <p class="text-lg md:text-xl gradient-text">
          A fast, secure debit card you can<br />
          use anytime, anywhere
        </p>
        <div class="hidden md:flex items-center justify-start">
          <p class="mr-4">Powered by</p>
          <img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Visa_Inc._logo.svg" alt="Visa" class="h-8 filter brightness-0" />
          <button class="ml-6 gradient-bg px-6 py-3 rounded-full flex items-center hover:opacity-90 transition w-64 justify-center">
            <span>Get Started</span>
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L12.586 11H5a1 1 0 110-2h7.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </button>
        </div>
      </div>
      
      <!-- Right Content - Card Images -->
      <div class="md:w-1/2 relative flex justify-center md:flex md:items-center">
        <div class="relative md:ml-16 mt-4 md:mt-0">
          <img 
            :src="cardImage" 
            alt="Finteca Card" 
            
          />
        </div>
      </div>
    </div>
    
    <!-- Mobile Only - Powered by VISA and Button -->
    <div class="fixed bottom-0 left-0 right-0 bg-white pb-4 pt-2 shadow-lg md:hidden z-40">
      <div class="flex flex-col items-center justify-center w-full">
        <div class="flex items-center justify-center mb-2">
          <p class="mr-4 text-gray-600 text-sm">Powered by</p>
          <img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Visa_Inc._logo.svg" alt="Visa" class="h-6 filter brightness-0" />
        </div>
        <button class="gradient-bg px-10 py-3 rounded-full flex items-center hover:opacity-90 transition w-64 justify-center">
          <span>Get Started</span>
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M10.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L12.586 11H5a1 1 0 110-2h7.586l-2.293-2.293a1 1 0 010-1.414z" clip-rule="evenodd" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Component-specific styles can go here */
@media (max-width: 768px) {
  .min-h-screen {
    padding-bottom: 80px; /* Ensure enough space at the bottom for the fixed button */
  }
}

/* Consistent button styling */
.gradient-bg {
  min-width: 256px; /* w-64 equivalent */
  max-width: 256px; /* w-64 equivalent */
  white-space: nowrap;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 48px; /* Consistent height */
  font-size: 16px; /* Consistent font size */
  box-sizing: border-box;
}

/* Ensure button maintains consistent appearance on all devices */
@media (min-width: 768px) and (max-width: 1024px) {
  .gradient-bg {
    /* Specific adjustments for iPad/tablet sizes */
    min-width: 256px !important;
    max-width: 256px !important;
  }
}
</style>
