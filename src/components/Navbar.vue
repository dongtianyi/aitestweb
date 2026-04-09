<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="navbar-container">
      <!-- Logo -->
      <a href="#" class="logo">
        <span class="logo-text">Roodle</span>
      </a>
      
      <!-- 导航链接 -->
      <ul class="nav-links">
        <li><a href="#features">功能</a></li>
        <li><a href="#advantages">优势</a></li>
        <li><a href="#reviews">评价</a></li>
        <li><a href="#about">关于</a></li>
      </ul>
      
      <!-- CTA 按钮 -->
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

<style scoped lang="scss">
@import '../styles/variables.scss';

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 72px;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  z-index: 1000;
  transition: all 0.3s ease;
  
  &.scrolled {
    background: rgba(0, 0, 0, 0.95);
    border-bottom-color: rgba(255, 255, 255, 0.15);
  }
  
  .navbar-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  .logo {
    text-decoration: none;
    
    .logo-text {
      font-size: 28px;
      font-weight: 700;
      color: $primary-green;
      letter-spacing: 1px;
    }
  }
  
  .nav-links {
    display: flex;
    gap: 40px;
    list-style: none;
    
    @media (max-width: $breakpoint-md) {
      display: none;
    }
    
    a {
      color: $text-secondary;
      text-decoration: none;
      font-size: $text-base;
      font-weight: $font-medium;
      transition: color 0.3s ease;
      
      &:hover {
        color: $primary-green;
      }
    }
  }
  
  .btn-download {
    background: $primary-green;
    color: #000;
    padding: 10px 24px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: $font-semibold;
    transition: all 0.3s ease;
    
    &:hover {
      transform: translateY(-2px);
      box-shadow: $shadow-glow;
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 8px 16px;
      font-size: $text-sm;
    }
  }
}
</style>
