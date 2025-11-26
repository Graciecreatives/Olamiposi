<template>
  <section
    class="w-full min-h-screen bg-[#D3DFEF] flex flex-col-reverse md:flex-row items-center justify-center px-6 md:px-16 py-10 gap-10"
  >
    <!-- TEXT SECTION (LEFT) -->
    <div 
      class="w-full md:w-1/2 text-center md:text-left space-y-4"
      data-aos="fade-right"
      data-aos-duration="1200"
    >
      <h1 class="text-4xl md:text-6xl font-bold text-[#2F0F09] leading-tight" data-aos="fade-up" data-aos-duration="1200">
        Happy Birthday,
        <span class="text-[#e70d86]">{{ celebrantName }}!</span>
      </h1>

      <p class="text-lg text-[#2F0F09]/80" data-aos="fade-up" data-aos-delay="200" data-aos-duration="1200">
        Wishing you joy, beauty, and endless happiness today and always.
        You are cherished, loved, and absolutely amazing. 💖
      </p>

      <!-- BUTTON WITH CONFETTI -->
      <button
        @click="celebrate"
        class="mt-4 bg-[#e70d86] text-white px-6 py-3 rounded-xl shadow-lg hover:bg-[#2F0F09] transition-all"
        data-aos="zoom-in"
        data-aos-delay="400"
      >
        Celebrate Her 🎉
      </button>
    </div>

    <!-- IMAGE CAROUSEL (RIGHT) -->
    <div 
      class="w-full md:w-1/2 flex justify-center"
      data-aos="fade-left"
      data-aos-duration="1200"
    >
      <div
        class="w-96 h-96 rounded-2xl overflow-hidden shadow-xl border-4 border-[#e70d86] relative"
      >
        <img
          :src="images[currentIndex]"
          alt="Celebrant"
          class="w-full h-full object-cover transition-all duration-700"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import Olamiposi1 from "@/assets/Images/Olamiposi1.jpg";
import Olamiposi2 from "@/assets/Images/Olamiposi2.jpg";
import Olamiposi3 from "@/assets/Images/Olamiposi3.jpg";

// Images array
const images = [Olamiposi1, Olamiposi2, Olamiposi3];
const celebrantName = "Nurse Olamiposi Odedeji";

// Carousel index
const currentIndex = ref(0);
onMounted(() => {
  setInterval(() => {
    currentIndex.value = (currentIndex.value + 1) % images.length;
  }, 3000);
});

// CONFETTI FUNCTION
const celebrate = () => {
  confetti({
    particleCount: 200,
    spread: 100,
    origin: { y: 0.6 }
  });

  setTimeout(() => {
    confetti({
      particleCount: 120,
      spread: 120,
    });
  }, 500);
};
</script>
