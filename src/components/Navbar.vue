<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <!-- 固定左上角图标 -->
    <div class="fixed-logo">
      <img src="/logo.jpg" alt="Roodle" class="fixed-logo-icon" />
    </div>
    
    <div class="navbar-container">
      <ul class="nav-links">
        <li><a href="#features">功能</a></li>
        <li><a href="#advantages">优势</a></li>
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

// 固定左上角图标
.fixed-logo {
  position: fixed;
  top: 20px;
  left: 20px;
  z-index: 1001;
  
  .fixed-logo-icon {
    width: 48px;
    height: 48px;
    border-radius: 12px;
    background: rgba(255, 255, 255, 0.9);
    backdrop-filter: blur(20px) saturate(180%);
    -webkit-backdrop-filter: blur(20px) saturate(180%);
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
    padding: 8px;
    transition: all $transition-base;
    
    &:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.12);
    }
    
    @media (max-width: $breakpoint-sm) {
      width: 40px;
      height: 40px;
      padding: 6px;
    }
  }
}

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
    justify-content: flex-end;
    gap: 32px;
    
    @media (max-width: $breakpoint-md) {
      padding: 0 16px;
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
    background: $primary-green;
    color: #FFFFFF;
    padding: 10px 20px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 600;
    font-size: $text-sm;
    transition: all $transition-base;
    
    &:hover {
      background: darken($primary-green, 10%);
      transform: translateY(-1px);
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 8px 16px;
      font-size: $text-xs;
    }
  }
}
</style>
