<template>
  <footer class="w-full bg-[#2F0F09] text-[#D3DFEF] py-8 px-6 md:px-16 flex flex-col md:flex-row items-center justify-between gap-4">
    <!-- Left side: copyright / credit -->
    <p class="text-sm md:text-base text-center md:text-left">
      &copy; {{ new Date().getFullYear() }} Made with ❤️ from GracieCreatives.
    </p>

    <!-- Right side: optional message or small links -->
    <p class="text-sm md:text-base text-center md:text-right">
      Designed with love for Nurse Olamiposi Odedeji 🎉
    </p>
  </footer>
</template>

<script setup>
// Nothing needed here since we're using JS Date in template
</script>

<style scoped>
footer p {
  line-height: 1.5;
}
</style>
