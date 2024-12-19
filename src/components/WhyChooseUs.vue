<template>
  <section class="lg:block bg-gradient-to-r from-[#160101] to-[#151212] py-6 md:py-16 md:px-16">
    <div class="text-3xl md:text-3xl lg:text-4xl font-bold bg-gradient-to-r from-red to-[#f5f5f5] bg-clip-text text-center py-10 mb-4 md:mb-8 text-transparent">
      Why choose RedNotice
    </div>

    <div class="md:grid lg:flex gap-6 text-white">
      <img src="/img/Rectangle 6.svg" class="px-6" alt="" />
      <main class="flex-1 p-4">
        <div class="flex flex-col md:flex-row gap-6">
          
          <div class="space-y-6 px-6 md:px-0">
            <div
              v-for="(card, index) in sideCards"
              :key="index"
              class="relative p-6 bg-center bg-cover  shadow-md border border-gray-700 text-center text-white rounded-3xl"
               style="background-image: url('/img/7637c246392da89e106d50b274bc3ef4 1.png');"
            >
            <div class="absolute inset-0 bg-red opacity-25 rounded-3xl"></div>
             
              <div class="relative z-10 ">
                <h3 class="text-lg font-bold text-red">{{ card.title }}</h3>
                <p class="text-sm mt-2">{{ card.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </main>
    </div>
  </section>
</template>

<script setup>
const sideCards = [
  {
    title: "Comprehensive Protection, Simplified",
    description:
      "RedNotice leverages AI to provide seamless, integrated security to cyber attacks, delivering actionable results effectively.",
    imageUrl: "/img/7637c246392da89e106d50b274bc3ef4 1.png",
  },
  {
    title: "Brand Integrity",
    description:
      "RedNotice monitors various platforms to protect your brand from unauthorized use and impersonation.",
    imageUrl: "/img/7637c246392da89e106d50b274bc3ef4 1.png",
  },
  {
    title: "Dark Web Surveillance",
    description:
      "Proactively monitor the dark web to prevent data leaks and unauthorized access to your sensitive information.",
    imageUrl: "/img/7637c246392da89e106d50b274bc3ef4 1.png",
  },
];

</script>