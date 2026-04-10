<template>
  <div class="app">
    <Navbar />
    <main>
      <Hero />
      <Features />
      <Advantages />
      <Download />
    </main>
    <Footer />
  </div>
</template>

<script setup lang="ts">
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import Advantages from './components/Advantages.vue'
import Download from './components/Download.vue'
import Footer from './components/Footer.vue'
</script>

<style lang="scss">
@import './styles/global-stresswatch.scss';

.app {
  min-height: 100vh;
  background: #F8F7F6;
}
</style>
