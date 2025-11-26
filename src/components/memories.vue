<template>
  <!-- MEMORIES SECTION -->
  <section class="w-full bg-[#D3DFEF] px-6 md:px-16 py-16">
    <!-- Section Title -->
    <h2
      class="text-3xl md:text-5xl font-bold text-[#2F0F09] mb-10 text-center"
      data-aos="fade-down"
      data-aos-duration="1200"
    >
      Memories 📸
    </h2>

    <!-- Responsive Image Grid -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div
        v-for="(image, index) in images"
        :key="index"
        class="overflow-hidden rounded-2xl shadow-lg"
        :data-aos="index % 2 === 0 ? 'fade-right' : 'fade-left'"
        data-aos-duration="1200"
        :data-aos-delay="index * 150"
      >
        <img
          :src="image"
          alt="Memory"
          class="w-full h-96 md:h-[550px] object-cover transform transition-transform duration-500 hover:scale-105"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import Img1 from '@/assets/Images/Olamiposi1.jpg';
import Img2 from '@/assets/Images/Olamiposi2.jpg';
import Img3 from '@/assets/Images/Olamiposi3.jpg';
import Img4 from '@/assets/Images/Olamiposi4.jpg';
import Img5 from '@/assets/Images/Olamiposi5.jpg';
import Img6 from '@/assets/Images/Olamiposi6.jpg';

const images = [Img1, Img2, Img3, Img4, Img5, Img6];
</script>
