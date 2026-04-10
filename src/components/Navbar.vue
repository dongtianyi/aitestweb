<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="navbar-container">
      <a href="#" class="logo">
        <span class="logo-text">ROODLE</span>
        <span class="logo-sub">AI POWERED</span>
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
  isScrolled.value = window.scrollY > 100
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
  height: 80px;
  background: linear-gradient(180deg, rgba(5, 5, 7, 0.98) 0%, rgba(5, 5, 7, 0) 100%);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid transparent;
  z-index: 1000;
  transition: all $transition-base;
  
  &.scrolled {
    background: rgba(5, 5, 7, 0.98);
    border-bottom-color: rgba(255, 255, 255, 0.1);
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
  }
  
  .navbar-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 48px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    
    @media (max-width: $breakpoint-md) {
      padding: 0 24px;
    }
  }
  
  .logo {
    text-decoration: none;
    display: flex;
    flex-direction: column;
    
    .logo-text {
      font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
      font-size: 36px;
      font-weight: 700;
      letter-spacing: 0.15em;
      background: $gradient-fire;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      line-height: 1;
    }
    
    .logo-sub {
      font-family: $font-mono;
      font-size: 9px;
      color: $cyber-blue;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      margin-top: 2px;
    }
  }
  
  .nav-links {
    display: flex;
    gap: 56px;
    list-style: none;
    
    @media (max-width: $breakpoint-md) {
      display: none;
    }
    
    a {
      color: $text-secondary;
      text-decoration: none;
      font-size: 13px;
      font-weight: $font-medium;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: all $transition-base;
      position: relative;
      
      &::after {
        content: '';
        position: absolute;
        bottom: -6px;
        left: 0;
        width: 0;
        height: 2px;
        background: $gradient-fire;
        transition: width $transition-base;
      }
      
      &:hover {
        color: $text-primary;
        
        &::after {
          width: 100%;
        }
      }
    }
  }
  
  .btn-download {
    background: $gradient-fire;
    color: $void-black;
    padding: 14px 28px;
    border-radius: 100px;
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
    transition: all $transition-base;
    position: relative;
    overflow: hidden;
    
    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
      transition: left 0.5s ease;
    }
    
    &:hover::before {
      left: 100%;
    }
    
    &:hover {
      transform: translateY(-2px);
      box-shadow: 0 15px 40px rgba(255, 85, 0, 0.4);
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 10px 20px;
      font-size: 13px;
    }
  }
}
</style>
