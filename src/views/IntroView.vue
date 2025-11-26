<template>
  <div
    class="w-full h-screen bg-[#e70d86] flex flex-col items-center justify-center text-center relative overflow-hidden"
  >
    <!-- Sparkles / Fireworks Canvas -->
    <canvas ref="particlesCanvas" class="absolute top-0 left-0 w-full h-full"></canvas>

    <!-- Centered Content -->
    <div class="z-10 flex flex-col items-center justify-center gap-6">
      <!-- Happy Birthday Text -->
      <h1
        class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold text-white animate-bounce"
      >
        🎉 Happy Birthday Olamiposi! 🎉
      </h1>

      <!-- Progress Bar Container -->
      <div class="w-3/4 max-w-md h-4 bg-white/40 rounded-full overflow-hidden relative">
        <div
          class="h-full bg-white rounded-full transition-all relative"
          :style="{ width: progress + '%' }"
        >
          <!-- Mini Confetti Sparks -->
          <div
            v-for="(spark, index) in sparks"
            :key="index"
            class="absolute w-2 h-2 rounded-full bg-[#e70d86] opacity-100 animate-pop"
            :style="{ left: spark.left + '%', top: spark.top + 'px' }"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { useRouter } from "vue-router";

const particlesCanvas = ref(null);
const router = useRouter();
const progress = ref(0);

// Confetti sparks array
const sparks = ref([]);

onMounted(() => {
  // Load canvas-confetti for background fireworks
  const script = document.createElement("script");
  script.src =
    "https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js";
  script.onload = () => {
    const confetti = window.confetti;
    const duration = 4000; // 4 seconds of animation
    const end = Date.now() + duration;

    const frame = () => {
      confetti({
        particleCount: 5,
        angle: 60,
        spread: 55,
        origin: { x: 0 },
      });
      confetti({
        particleCount: 5,
        angle: 120,
        spread: 55,
        origin: { x: 1 },
      });

      if (Date.now() < end) requestAnimationFrame(frame);
    };
    frame();
  };
  document.body.appendChild(script);

  // Animate progress bar and generate mini confetti
  let start = null;
  const duration = 5000; // 5 seconds

  const animateProgress = (timestamp) => {
    if (!start) start = timestamp;
    const elapsed = timestamp - start;
    progress.value = Math.min((elapsed / duration) * 100, 100);

    // Add mini confetti sparks randomly along the progress
    if (Math.random() > 0.6 && progress.value < 100) {
      sparks.value.push({
        left: progress.value,
        top: Math.random() * 4, // small vertical offset
      });
      if (sparks.value.length > 30) sparks.value.shift(); // keep max sparks
    }

    if (elapsed < duration) {
      requestAnimationFrame(animateProgress);
    }
  };
  requestAnimationFrame(animateProgress);

  // Navigate to /home after 5 seconds
  setTimeout(() => {
    router.push("/home");
  }, duration);
});
</script>

<style scoped>
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-4px); }
}

.animate-bounce {
  animation: bounce 1s infinite;
}

/* Mini confetti pop animation */
@keyframes pop {
  0% { transform: translateY(0) scale(1); opacity: 1; }
  50% { transform: translateY(-10px) scale(1.5); opacity: 0.8; }
  100% { transform: translateY(-20px) scale(0); opacity: 0; }
}

.animate-pop {
  animation: pop 0.8s forwards;
}
</style>
