<template>
  <!-- BIRTHDAY WISHES SECTION -->
  <section
    class="w-full bg-white px-6 md:px-16 py-16 flex flex-col-reverse md:flex-row items-center gap-12"
  >
    <!-- TEXT SECTION (LEFT) -->
    <div
      class="w-full md:w-1/2 space-y-4 order-2 md:order-1 text-center md:text-left"
      data-aos="fade-right"
      data-aos-duration="1200"
    >
      <h2 class="text-3xl md:text-5xl font-bold text-[#2F0F09] mb-4" data-aos="fade-up" data-aos-duration="1200">
        Heartfelt Birthday Wishes 💖
      </h2>

      <p class="text-lg text-[#2F0F09]/80 leading-relaxed" data-aos="fade-up" data-aos-delay="100" data-aos-duration="1200">
        Happy Birthday my Love, <span class="font-semibold text-[#e70d86]">Nurse Olamiposi Odedeji</span>! 🎉  
        From the days we laughed as kids to now, watching you grow into the incredible woman you are today has been one of my greatest joys.
      </p>

      <p class="text-lg text-[#2F0F09]/80 leading-relaxed" data-aos="fade-up" data-aos-delay="200" data-aos-duration="1200">
        I am so proud of your strength, your kindness, and the way you chase your dreams with unwavering determination.  
        You inspire everyone around you, and I feel so lucky to witness your journey firsthand.
      </p>

      <p class="text-lg text-[#2F0F09]/80 leading-relaxed" data-aos="fade-up" data-aos-delay="300" data-aos-duration="1200">
        May this year bring you endless happiness, love, and all the beautiful moments you deserve.  
        Keep shining, keep dreaming, and never forget how deeply loved and cherished you are. ✨
      </p>
    </div>

    <!-- VIDEO SECTION (RIGHT) -->
    <div
      class="w-full md:w-1/2 flex justify-center order-1 md:order-2"
      data-aos="fade-left"
      data-aos-duration="1200"
    >
      <div class="w-80 h-80 md:w-[420px] md:h-[420px] rounded-2xl overflow-hidden shadow-xl border-4 border-[#e70d86] relative">
        <video
          class="w-full h-full object-cover"
          autoplay
          muted
          loop
          playsinline
          :src="BirthdayVideo"
        ></video>
      </div>
    </div>
  </section>
</template>

<script setup>
import BirthdayVideo from '@/assets/Video/BirthdayVideo.mp4';
</script>
