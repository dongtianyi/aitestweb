<template>
  <div class="app">
    <!-- 全局背景效果 -->
    <div class="bg-grid"></div>
    <div class="gradient-orb orb-1"></div>
    <div class="gradient-orb orb-2"></div>
    <div class="gradient-orb orb-3"></div>
    <div class="noise-overlay"></div>
    <div class="cursor-dot"></div>
    <div class="cursor-ring"></div>
    
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
import { onUnmounted } from 'vue'
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import Advantages from './components/Advantages.vue'
import Download from './components/Download.vue'
import Footer from './components/Footer.vue'

// 自定义光标逻辑
const cursorDot = document.querySelector('.cursor-dot') as HTMLElement
const cursorRing = document.querySelector('.cursor-ring') as HTMLElement
const interactiveElements = document.querySelectorAll('a, button, .feature-card, .metric-item, .store-btn')

let cursorX = 0
let cursorY = 0
let ringX = 0
let ringY = 0

const updateCursor = () => {
  if (cursorDot && cursorRing) {
    cursorDot.style.left = cursorX - 4 + 'px'
    cursorDot.style.top = cursorY - 4 + 'px'
    cursorRing.style.left = ringX - 20 + 'px'
    cursorRing.style.top = ringY - 20 + 'px'
  }
  requestAnimationFrame(updateCursor)
}

document.addEventListener('mousemove', (e) => {
  cursorX = e.clientX
  cursorY = e.clientY
  
  // 光环有轻微延迟跟随
  setTimeout(() => {
    ringX = e.clientX
    ringY = e.clientY
  }, 50)
})

if (!cursorDot || !cursorRing) {
  requestAnimationFrame(updateCursor)
}

// 悬停效果
interactiveElements.forEach(el => {
  el.addEventListener('mouseenter', () => document.body.classList.add('cursor-hover'))
  el.addEventListener('mouseleave', () => document.body.classList.remove('cursor-hover'))
})

// 清理
onUnmounted(() => {
  interactiveElements.forEach(el => {
    el.removeEventListener('mouseenter', () => document.body.classList.add('cursor-hover'))
    el.removeEventListener('mouseleave', () => document.body.classList.remove('cursor-hover'))
  })
})
</script>

<style lang="scss">
@import './styles/variables.scss';
@import './styles/global.scss';

.app {
  min-height: 100vh;
  position: relative;
}
</style>
