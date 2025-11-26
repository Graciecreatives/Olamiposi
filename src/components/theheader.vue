<template>
  <header class="w-full bg-[#e70d86] py-4 overflow-hidden relative">
    <!-- Marquee Text -->
    <div class="w-full overflow-hidden">
      <div class="animate-marquee flex gap-12 whitespace-nowrap">
        <span class="text-white font-bold text-2xl sm:text-3xl md:text-4xl">
          🎉 Happy Birthday Olamiposi Odedeji! 🎉
        </span>
        <span class="text-white font-bold text-2xl sm:text-3xl md:text-4xl">
          🎉 Happy Birthday Olamiposi Odedeji! 🎉
        </span>
        <span class="text-white font-bold text-2xl sm:text-3xl md:text-4xl">
          🎉 Happy Birthday Olamiposi Odedeji! 🎉
        </span>
      </div>
    </div>
  </header>
</template>

<style scoped>
@keyframes marquee {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-33.333%); /* Moves one full set of repeated text */
  }
}

.animate-marquee {
  display: flex;
  gap: 3rem;
  animation: marquee 15s linear infinite;
}
</style>
