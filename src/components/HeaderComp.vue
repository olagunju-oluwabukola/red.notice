<template>
  <header class="fixed top-0 left-0 w-full bg-black text-white z-50">
    <div class="container mx-auto flex justify-between items-center p-4">
      <!-- Logo -->
      <div class="text-2xl font-bold flex items-center">
        <img
          src="/img/R_N_1-removebg-preview.png"
          alt="Cyber Defense Icon"
          class="max-w-full h-auto"
        />
      </div>

      <nav class="hidden lg:block space-x-6 text-[#F5F5F5] text-[14px] md:text-[20px]">
        <router-link to="/" class="text-[#C30000]">Home</router-link>
        <a href="#" class="hover:text-red">Company</a>
        <a href="#" class="hover:text-red">Solutions</a>
        <a href="#" class="hover:text-red">Pricing</a>
        <a href="#" class="hover:text-red">Blog</a>
      </nav>

      <!-- Desktop Action Buttons -->
      <div class="hidden lg:flex space-x-4 items-center text-[#F5F5F5] text-[20px]">
        <router-link to="/login" class="flex items-center space-x-2 hover:underline">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2"
            stroke="currentColor"
            class="w-6 h-6 p-1 icon"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"
            />
          </svg>
          <span>Sign In</span>
        </router-link>
        <button
          v-if="!isDashboardPage"
          class="px-4 py-2 bg-gradient-to-r from-red to-black rounded-2xl shadow-md hover:opacity-90 text-white"
        >
          <router-link to="/request-demo">Request a Demo</router-link>
        </button>
      </div>

      <!-- Mobile & Tablet Menu Toggle -->
      <button @click="toggleMobileMenu" class="block lg:hidden focus:outline-none">
        <svg
          v-if="!isMobileMenuOpen"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
    </div>

    <!-- Mobile & Tablet Menu -->
    <div v-if="isMobileMenuOpen" class="lg:hidden bg-black">
      <nav class="space-y-2 p-4 text-[#F5F5F5]">
        <router-link to="/" class="block text-red hover:text-white">Home</router-link>
        <a href="#" class="block text-white hover:text-red-600">Company</a>
        <a href="#" class="block text-white hover:text-red-600">Solutions</a>
        <a href="#" class="block text-white hover:text-red-600">Pricing</a>
        <a href="#" class="block text-white hover:text-red-600">Blog</a>
        <router-link
          to="/login"
          class="flex items-center space-x-2 text-white hover:underline mt-4"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2"
            stroke="currentColor"
            class="w-6 h-6 border border-rounded"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"
            />
          </svg>
          <span>Sign In</span>
        </router-link>
        <button
          v-if="!isDashboardPage"
          class="w-full px-4 py-2 bg-gradient-to-r from-red to-black text-white rounded-md shadow-md hover:opacity-90"
        >
          <router-link to="/request-demo">Request a Demo</router-link>
        </button>
      </nav>
    </div>
  </header>
</template>

<script>
import { ref, computed } from "vue";
import { useRoute } from "vue-router";

export default {
  setup() {
    const isMobileMenuOpen = ref(false);
    const route = useRoute();

    const toggleMobileMenu = () => {
      isMobileMenuOpen.value = !isMobileMenuOpen.value;
    };

    const isDashboardPage = computed(() => route.path === "/user-dashboard");

    return { isMobileMenuOpen, toggleMobileMenu, isDashboardPage };
  },
};
</script>
