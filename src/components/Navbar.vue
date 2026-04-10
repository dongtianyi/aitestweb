<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="navbar-container">
      <a href="#" class="logo">
        <span class="logo-text">Roodle</span>
      </a>
      
      <ul class="nav-links">
        <li><a href="#features">功能</a></li>
        <li><a href="#advantages">优势</a></li>
        <li><a href="#reviews">评价</a></li>
        <li><a href="#about">关于</a></li>
      </ul>
      
      <a href="#download" class="btn-download">免费下载</a>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style lang="scss">
@import '../styles/variables-stresswatch.scss';

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 72px;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%);
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  z-index: 1000;
  transition: all $transition-base;
  
  &.scrolled {
    background: rgba(255, 255, 255, 0.95);
    box-shadow: 0 2px 16px rgba(0, 0, 0, 0.04);
  }
  
  .navbar-container {
    max-width: 1116px;
    margin: 0 auto;
    padding: 0 24px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    
    @media (max-width: $breakpoint-md) {
      padding: 0 16px;
    }
  }
  
  .logo {
    text-decoration: none;
    
    .logo-text {
      font-size: 24px;
      font-weight: 700;
      color: $text-primary;
      letter-spacing: -0.02em;
    }
  }
  
  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
    
    @media (max-width: $breakpoint-md) {
      display: none;
    }
    
    a {
      color: $text-secondary;
      text-decoration: none;
      font-size: $text-sm;
      font-weight: $font-medium;
      transition: all $transition-base;
      
      &:hover {
        color: $text-primary;
      }
    }
  }
  
  .btn-download {
    background: #007AFF;
    color: #FFFFFF;
    padding: 10px 20px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 600;
    font-size: $text-sm;
    transition: all $transition-base;
    
    &:hover {
      background: #0056CC;
      transform: translateY(-1px);
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 8px 16px;
      font-size: $text-xs;
    }
  }
}
</style>
