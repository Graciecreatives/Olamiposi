<template>
  <!-- CELEBRATION SECTION -->
  <section
    class="w-full bg-[#e70d86]/20 py-16 md:py-24 flex flex-col items-center justify-center text-center relative overflow-hidden px-4 md:px-16"
  >
    <!-- Confetti Canvas -->
    <canvas ref="confettiCanvas" class="absolute top-0 left-0 w-full h-full pointer-events-none"></canvas>

    <!-- Celebration Text -->
    <h2
      class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-[#2F0F09] mb-4 sm:mb-6"
      data-aos="fade-down"
      data-aos-duration="1200"
    >
      🎉 Dear Olamiposi
    </h2>

    <p
      class="text-base sm:text-lg md:text-xl lg:text-2xl text-[#2F0F09]/80 mb-6 sm:mb-8 max-w-xl leading-relaxed"
      data-aos="fade-up"
      data-aos-duration="1200"
      data-aos-delay="200"
    >
      You're stronger than you think, and the best is yet to come.  
      May your dreams come true, your wishes be fulfilled,  
      and your heart always be filled with joy and love. 💖
    </p>

    <!-- Confetti Button -->
    <button
      @click="startConfetti"
      class="bg-[#e70d86] text-white px-5 sm:px-6 py-2 sm:py-3 rounded-xl shadow-lg hover:bg-[#2F0F09] transition-all text-sm sm:text-base md:text-lg"
      data-aos="zoom-in"
      data-aos-duration="1200"
      data-aos-delay="400"
    >
      Happy Birthday 🎊
    </button>
  </section>
</template>

<script setup>
import { ref } from "vue";

const confettiCanvas = ref(null);
let confettiInstance = null;

// Load canvas-confetti dynamically
const startConfetti = () => {
  if (!confettiInstance) {
    const script = document.createElement("script");
    script.src =
      "https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js";
    script.onload = () => {
      confettiInstance = window.confetti.create(confettiCanvas.value, {
        resize: true,
        useWorker: true,
      });
      triggerConfetti();
    };
    document.body.appendChild(script);
  } else {
    triggerConfetti();
  }
};

// Trigger confetti
const triggerConfetti = () => {
  confettiInstance({
    particleCount: 200,
    spread: 160,
    origin: { y: 0.6 },
  });
};
</script>

<style scoped>
canvas {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}
</style>
