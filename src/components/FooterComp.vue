<template>
    <footer class="bg-gradient-to-r from-[#160101] to-[#151212] text-white py-8">
      <div class="container mx-auto px-4">
        <!-- Top Section -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
          <img
          src="/img/R N 1.svg"
          alt="Cyber Defense Icon"
          class="h-6 md:h-14 w-1/2 "
        />
          <!-- Left Section: Links -->
          <div>
            <h2 class="text-lg font-semibold mb-4  bg-gradient-to-r from-red to-white bg-clip-text text-transparent">Product</h2>
            <ul class="space-y-3 md:space-y-6 text-sm">
              <li><a href="#" class="hover:text-red">Pricing</a></li>
              <li><a href="#" class="hover:text-red">Changelog</a></li>
              <li><a href="#" class="hover:text-red">Docs</a></li>
            </ul>
          </div>
  
          <div>
            <h2 class="text-lg font-semibold mb-4 bg-gradient-to-r from-red to-white bg-clip-text text-transparent">Company</h2>
            <ul class="space-y-3 md:space-y-6 text-sm">
              <li><a href="#" class="hover:text-red">About us</a></li>
              <li><a href="#" class="hover:text-red">Blog</a></li>
              <li><a href="#" class="hover:text-red">Careers</a></li>
              <li><a href="#" class="hover:text-red">Contact us</a></li>
            </ul>
          </div>
  
          <!-- Right Section: Subscription & Social Media -->
          <div>
            <h2 class="text-lg font-semibold mb-4 bg-gradient-to-r from-red to-white bg-clip-text text-transparent">Stay up to date</h2>
            <div class="relative flex items-center mb-4 w-full">
  <input
    type="email"
    placeholder="Enter your email"
    class="flex-1 px-3 py-2 pr-20 bg-gradient-to-r from-red to-black text-white rounded-2xl focus:outline-none"
  />

  <button
    class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-gradient-to-r from-red to-black text-white px-6 py-2 rounded-2xl"
  >
    Subscribe
  </button>
</div>

            <img src="/img/76744487f26d0848b00b56856a1539ba 1.svg"
            class="hidden md:flex"
            alt="">
            <!-- Social Media Icons -->
            <div class="flex justify-center space-x-6 mt-4" >
              
              <a href="#" class="hover:text-red">
                <svg 
  xmlns="http://www.w3.org/2000/svg" 
  viewBox="0 0 24 24" 
  fill="currentColor" 
  class="w-6 h-6"
>
  <path 
    d="M22.675 0H1.325C.593 0 0 .593 0 1.326v21.348C0 23.406.593 24 1.325 24h11.494v-9.294H9.577V11.09h3.242V8.413c0-3.21 1.963-4.957 4.829-4.957 1.372 0 2.553.102 2.895.148v3.36h-1.988c-1.56 0-1.863.741-1.863 1.83v2.398h3.727l-.486 3.616h-3.24V24h6.356c.73 0 1.325-.593 1.325-1.326V1.326C24 .593 23.406 0 22.675 0z"
  />
</svg>

              </a>
              <a href="#" class="hover:text-red">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="w-8 h-8 rounded"
                  fill="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M24 4.557a9.931 9.931 0 01-2.828.775 4.936 4.936 0 002.165-2.724 9.864 9.864 0 01-3.127 1.195 4.92 4.92 0 00-8.379 4.482A13.971 13.971 0 011.671 3.149a4.908 4.908 0 001.523 6.557 4.902 4.902 0 01-2.23-.616v.061a4.923 4.923 0 003.946 4.827 4.935 4.935 0 01-2.224.084 4.925 4.925 0 004.6 3.417 9.867 9.867 0 01-6.102 2.104c-.396 0-.787-.023-1.175-.067a13.945 13.945 0 007.548 2.212c9.055 0 14.007-7.504 14.007-14.007 0-.213-.005-.426-.014-.637A10.025 10.025 0 0024 4.557z"
                  />
                </svg>
              </a>
              <a href="#" class="hover:text-red ">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="w-8 h-8 rounded"
                  fill="currentColor"
                  viewBox="0 0 24 24"
                >
                  <path
                    d="M22.225 0H1.771C.791 0 0 .774 0 1.729v20.542C0 23.226.791 24 1.771 24h20.451C23.207 24 24 23.226 24 22.271V1.729C24 .774 23.207 0 22.225 0zM7.215 20.452H3.788V9h3.427v11.452zM5.504 7.452c-1.094 0-1.99-.895-1.99-1.991 0-1.097.896-1.991 1.99-1.991 1.096 0 1.99.894 1.99 1.991 0 1.096-.895 1.991-1.99 1.991zm13.618 13H15.69V14.66c0-1.386-.495-2.33-1.732-2.33-.947 0-1.509.645-1.758 1.267-.091.22-.114.527-.114.834V20.45H8.936s.045-10.684 0-11.784h3.381v1.675c.45-.696 1.258-1.694 3.067-1.694 2.238 0 3.919 1.462 3.919 4.608V20.45z"
                  />
                </svg>
              </a>
            </div>
          </div>
        </div>
  
        <!-- Bottom Section -->
        <div class="mt-8 border-t border-gray-700 pt-4  text-[14px]">
          <p>&copy; 2024 RedNotice. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    setup() {
      return {};
    },
  };
  </script>
  
  
  