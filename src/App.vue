<script setup lang="ts">
import NavView from './components/NavView.vue'
import HeroSection from './components/HeroSection.vue'
</script>

<template>
  <main class="bg-[#fff] hidden lg:block">
    <div class="w-full h-full bgForSection">
      <NavView/>
      <HeroSection/>
    </div>
  </main>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap');
html{
  height: 100%;
}
body, main{
  min-height: 100vh;
  font-family: 'Plus Jakarta Sans', sans-serif;
}
body::-webkit-scrollbar{
  width: 3px;
  background: transparent;
}
body::-webkit-scrollbar-track{
  background: #000;
}
body::-webkit-scrollbar-thumb{
  width: 3px;
  background: blue;
}
.bgForSection{
  background: url('/Image/passengerBg.png');
  background-repeat: no-repeat;
  background-position:contain;
  background-size: 100%;
}
</style>
