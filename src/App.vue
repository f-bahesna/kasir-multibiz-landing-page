<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import Pricing from './components/Pricing.vue'
import Testimonials from './components/Testimonials.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="app-wrapper">
    <Navbar />
    <main>
      <Hero />
      <Features />
      <Pricing />
      <Testimonials />
    </main>
    <Footer />
  </div>
</template>

<style scoped>
.app-wrapper {
  overflow-x: hidden;
}
</style>
