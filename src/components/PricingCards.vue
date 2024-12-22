<template>
    <section class="pricing-section">
      <div class="text-center mb-10">
        <h1 class="text-3xl md:text-3xl lg:text-4xl font-bold bg-gradient-to-r from-red to-[#F5F5F5] bg-clip-text text-transparent mt-10 md:mt-0">
          Simple and Transparent Pricing
        </h1>
        <p class="pricing-subtitle">
          No matter your situation, our offerings evolve to meet your needs.
        </p>
      </div>
      <div class="pricing-grid">
        <div
          v-for="(plan, index) in pricingPlans"
          :key="index"
          :class="`pricing-card card-${index + 1}`"
        >
          <div v-if="plan.isPopular" class="most-popular-badge">
            <span>Most Popular</span>
          </div>
          <h3 class="card-title my-4">{{ plan.title }}</h3>
          <p class="card-description text-sm my-3 md:my-5">{{ plan.description }}</p>
          <ul class="features-list">
            <li
              v-for="(feature, featureIndex) in plan.features"
              :key="featureIndex"
              class="feature-item"
            >
              <span class="checkmark mt-3 md:mt-5">✔</span>
              <span class="text-sm mt-3 md:mt-5">{{ feature }}</span>
            </li>
          </ul>
          <div class="button-container">
            <button
              v-if="plan.buttonText"
              :class="`btn btn-${index + 1}`"
            >
            <router-link to="/login">
                {{ plan.buttonText }}
            </router-link>
             
            </button>
            <button
              v-else
              :class="`btn btn-${index + 1}`"
            >
              Contact Us →
            </button>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { ref } from "vue";
  
  export default {
    setup() {
      const pricingPlans = ref([
        {
          title: "$20 /month",
          description:
            "Ideal for beginners or small businesses looking to start automating tasks.",
          features: [
            "1 user",
            "Free 1 month (no auto-renewal)",
            "Support engineer",
            "1 project",
            "2 workflows",
            "20 executions per day",
          ],
          buttonText: "Start",
          isPopular: false,
        },
        {
          title: "$10 /month",
          description: "Ideal for medium businesses with higher automation needs.",
          features: [
            "5 users",
            "Free 1 month (no auto-renewal)",
            "Support engineer",
            "2 projects",
            "10 workflows",
            "1500 executions per day",
          ],
          buttonText: "Start",
          isPopular: true,
        },
        {
          title: "$30 /month",
          description:
            "Exclusive plan for large businesses with complex and expansive automation needs.",
          features: [
            "7 users",
            "Free 1 month (no auto-renewal)",
            "Support engineer",
            "3 projects",
            "15 workflows",
            "2000 executions per day",
          ],
          buttonText: "Start",
          isPopular: false,
        },
        {
          title: "RedNotice Solution",
          description:
            "Full custom solution for large enterprises with high operational scale.",
          features: [
            "More than 7 users",
            "24/7 support engineer",
            "99.9% SLA",
            "Unlimited projects and workflows",
            "Unlimited executions per day",
            "Dedicated server",
          ],
          buttonText: null,
          isPopular: false,
        },
      ]);
  
      return { pricingPlans };
    },
  };
  </script>
  
  <style>
  
  .pricing-section {
    background: linear-gradient(to right, #160101, #151212);
    color: white;
    padding: 2rem 1rem;
  }
  
  .pricing-title {
    font-size: 2.5rem;
    font-weight: bold;
  }
  
  .pricing-subtitle {
    font-size: 1.125rem;
    margin-top: 0.5rem;
  }
  
  /* Grid Layout */
  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 1.5rem;
    padding: 0 1.5rem;
  }
  
  @media (min-width: 640px) {
    .pricing-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (min-width: 1024px) {
    .pricing-grid {
      grid-template-columns: repeat(4, 1fr);
    }
  }
  
  /* Card Styles */
  .pricing-card {
    padding: 1.5rem;
    border-radius: 0.5rem;
    text-align: center;
    transition: transform 0.2s ease-in-out;
  }
  
  .pricing-card:hover {
    transform: scale(1.05); 
  }
  
  
  .card-1 {
    border: 2px solid #ff5733;
  }
  
  .card-2 {
    border: 5px solid #C30000
  }
  
  .card-3 {
    border: 2px solid #F5F5F5;
  }
  
  .card-4 {
    border: 2px solid #ff33a1;
  }
  
 
  .most-popular-badge {
    margin-bottom: 1rem;
  }
  
  .most-popular-badge span {
    background: linear-gradient(to right, red, black);
    color: white;
    padding: 0.6rem 1rem;
    border-radius: 9999px;
    font-size: 0.875rem;
    text-transform: uppercase;
  }
  
  
  .btn {
    padding: 0.75rem 1.5rem;
    border-radius: 1rem;
    font-size: 1rem;
    font-weight: bold;
    color: white;
    cursor: pointer;
    transition: transform 0.2s ease-in-out;
    width: 100%;
  }
  
  .btn:hover {
    transform: scale(1.1); 
  }
  
  .btn-1 {
    background-color: #ff5733;
  }
  
  .btn-1:hover {
    background-color: #e64d2a;
  }
  
  .btn-2 {
    background-color:  #C30000;
  }
  
  
  
  .btn-3 {
    background-color: #f5f5f5;
    color: #c30000;
  }
  
  .btn-3:hover {
    background-color: #c30000;
    color: white;
  }
  
  .btn-4 {
    background-color: #ff33a1;
  }
  
  .btn-4:hover {
    background-color: #e62a8c;
  }
  
  /* Features List */
  .features-list {
    margin-bottom: 1.5rem;
  }
  
  .feature-item {
    display: flex;
    align-items: center;
    justify-content: start;
  }
  
  .checkmark {
    color: #4caf50;
    margin-right: 0.5rem;
  }
  </style>
  