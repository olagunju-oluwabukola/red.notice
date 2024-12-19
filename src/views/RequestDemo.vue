<template>
    <div class="flex flex-col md:flex-row h-screen bg-gradient-to-r from-[#160101] to-[#151212] text-white">
      <!-- Left Section (Form) -->
      <div class="flex-1 flex flex-col justify-center items-center p-8 md:p-16 bg-gradient-to-b from-red-900 to-black">
        <!-- Header -->
        <div>
          <h1 class="mb-4 md:mb-8 text-xl md:text-3xl lg:text-4xl font-bold bg-gradient-to-r from-red to-white bg-clip-text text-transparent">
            Request a Demo Today
          </h1>
          <p class="my-3 md:my-8 md:text-lg text-sm">
            Discover how RedNotice can revolutionize your business with our cutting-edge cyber intelligence solutions.
          </p>
        </div>
  
        <!-- Form -->
        <form @submit.prevent="handleRequestDemo" class="w-full mt-5 md:mt-10 max-w-md space-y-4">
          <input
            v-model="form.name"
            type="text"
            placeholder="Your Name"
            class="w-full cards border-gray-400 text-white p-3 rounded-lg focus:ring-2 focus:ring-red-500 outline-none"
            required
          />
  
          <input
            v-model="form.email"
            type="email"
            placeholder="Your Email"
            class="w-full cards border-gray-400 text-white p-3 rounded-lg focus:ring-2 focus:ring-red-500 outline-none"
            required
          />
  
          <textarea
            v-model="form.message"
            placeholder="Your Message"
            class="w-full cards border-gray-400 text-white p-3 rounded-lg focus:ring-2 focus:ring-red-500 outline-none"
            rows="4"
            required
          ></textarea>
  
          <button
            type="submit"
            class="w-full bg-gradient-to-r from-red to-black text-white px-6 py-3 rounded-lg"
          >
            Request Demo
          </button>
        </form>
  
        <!-- Popup Modal -->
        <div v-if="popupMessage" class="fixed inset-0 bg-gradient-to-r from-[#160101] to-[#151212] bg-opacity-75 flex items-center justify-center">
          <div class="bg-white text-black p-6 rounded-lg shadow-lg">
            <p>{{ popupMessage }}</p>
            <button
              class="mt-4 px-4 py-2 bg-red text-white rounded-lg hover:bg-red-800"
              @click="closePopup"
            >
              Close
            </button>
          </div>
        </div>
      </div>
  
      <!-- Right Section (Image) -->
      <div class="hidden md:hidden lg:flex flex-1 items-center justify-center">
        <img
          src="/img/mmmmmmmmmmmmmmmm 1.png"
          alt="Demo Illustration"
          class="max-w-full max-h-full object-contain"
        />
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from "vue";
  import { useRouter } from "vue-router";
  
  export default {
    setup() {
      const router = useRouter();
      const form = ref({
        name: "",
        email: "",
        message: "",
      });
      const popupMessage = ref("");
  
      const closePopup = () => {
        popupMessage.value = "";
      };
  
      const handleRequestDemo = async () => {
        try {
          const response = await fetch("http://127.0.0.1:8000/api/v1/request-demo", {
            method: "POST",
            headers: {
              "Content-Type": "application/json",
            },
            body: JSON.stringify(form.value),
          });
  
          if (!response.ok) {
            throw new Error("Failed to submit the demo request.");
          }
  
          form.value.name = "";
          form.value.email = "";
          form.value.message = "";
  
          popupMessage.value = "Your demo request has been submitted successfully!";
        } catch (error) {
          popupMessage.value = "An error occurred. Please try again.";
          console.error("Error:", error);
        }
      };
  
      return { form, popupMessage, closePopup, handleRequestDemo };
    },
  };
  </script>
  
  <style scoped>
  body {
    font-family: "Arial", sans-serif;
  }
  </style>
  