<template>
  <section class="hero">
    <div class="hero-container">
      <!-- 导航占位 -->
      <div class="hero-spacer"></div>
      
      <!-- 主内容 -->
      <div class="hero-content">
        <div class="hero-badge">
          <span class="badge-icon">🏃</span>
          <span>专业跑步分析</span>
        </div>
        
        <h1 class="hero-title">
          让每一步<br/>
          <span class="text-gradient">都有数据支撑</span>
        </h1>
        
        <p class="hero-subtitle">
          Roodle 是你的智能跑步教练，通过 AI 数据分析，
          帮助你科学训练、预防损伤、突破个人最佳。
        </p>
        
        <div class="hero-cta">
          <a href="#download" class="btn-primary">
            <span>免费下载</span>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
          <a href="#features" class="btn-secondary">
            了解功能
          </a>
        </div>
        
        <!-- 信任标识 -->
        <div class="hero-trust">
          <div class="trust-item">
            <span class="trust-number">50K+</span>
            <span class="trust-label">活跃用户</span>
          </div>
          <div class="trust-divider"></div>
          <div class="trust-item">
            <span class="trust-number">4.9</span>
            <span class="trust-label">App Store 评分</span>
          </div>
          <div class="trust-divider"></div>
          <div class="trust-item">
            <span class="trust-number">1M+</span>
            <span class="trust-label">累计跑量</span>
          </div>
        </div>
      </div>
      
      <!-- APP Mockup -->
      <div class="hero-mockup">
        <div class="phone-frame">
          <div class="phone-screen">
            <img src="/app-screenshot.jpg" alt="Roodle App 截图" class="app-screenshot" />
          </div>
        </div>
        <!-- 装饰元素 -->
        <div class="mockup-glow"></div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style lang="scss">
@import '../styles/variables-stresswatch.scss';

.hero {
  min-height: 100vh;
  background: $bg-primary;
  position: relative;
  overflow: hidden;
  
  .hero-spacer {
    height: 80px;
    
    @media (max-width: $breakpoint-md) {
      height: 60px;
    }
  }
  
  .hero-container {
    max-width: 1116px;
    margin: 0 auto;
    padding: 60px 24px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    
    @media (max-width: $breakpoint-lg) {
      grid-template-columns: 1fr;
      text-align: center;
      gap: 60px;
    }
    
    @media (max-width: $breakpoint-md) {
      padding: 40px 16px;
      gap: 48px;
    }
  }
  
  .hero-content {
    @media (max-width: $breakpoint-lg) {
      order: 2;
    }
  }
  
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(0, 122, 255, 0.1);
    border-radius: $radius-full;
    padding: 6px 16px;
    margin-bottom: 24px;
    
    .badge-icon {
      font-size: 16px;
    }
    
    span {
      font-size: $text-sm;
      font-weight: $font-medium;
      color: $primary-green;
    }
  }
  
  .hero-title {
    font-size: $text-hero;
    font-weight: $font-bold;
    color: $text-primary;
    line-height: 1.1;
    margin-bottom: 24px;
    letter-spacing: -0.02em;
    
    @media (max-width: $breakpoint-md) {
      font-size: $text-4xl;
    }
    
    @media (max-width: $breakpoint-sm) {
      font-size: $text-3xl;
    }
    
    .text-gradient {
      background: linear-gradient(135deg, $primary-green 0%, #5AC8FA 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
  }
  
  .hero-subtitle {
    font-size: $text-xl;
    color: $text-secondary;
    line-height: 1.6;
    margin-bottom: 32px;
    max-width: 480px;
    
    @media (max-width: $breakpoint-lg) {
      margin-left: auto;
      margin-right: auto;
      max-width: 100%;
    }
    
    @media (max-width: $breakpoint-sm) {
      font-size: $text-lg;
    }
  }
  
  .hero-cta {
    display: flex;
    gap: 16px;
    margin-bottom: 48px;
    
    @media (max-width: $breakpoint-lg) {
      justify-content: center;
    }
    
    @media (max-width: $breakpoint-sm) {
      flex-direction: column;
      gap: 12px;
    }
    
    .btn-primary {
      background: $primary-green;
      color: #FFFFFF;
      padding: 16px 32px;
      border-radius: 14px;
      font-size: $text-lg;
      font-weight: $font-semibold;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: all $transition-base;
      box-shadow: 0 4px 16px rgba($primary-green, 0.3);
      
      &:hover {
        background: darken($primary-green, 10%);
        transform: translateY(-2px);
        box-shadow: 0 8px 24px rgba($primary-green, 0.4);
      }
      
      svg {
        transition: transform $transition-base;
      }
      
      &:hover svg {
        transform: translateX(4px);
      }
    }
    
    .btn-secondary {
      background: rgba(0, 0, 0, 0.05);
      color: $text-primary;
      padding: 16px 32px;
      border-radius: 14px;
      font-size: $text-lg;
      font-weight: $font-medium;
      text-decoration: none;
      display: flex;
      align-items: center;
      transition: all $transition-base;
      
      &:hover {
        background: rgba(0, 0, 0, 0.1);
      }
    }
  }
  
  .hero-trust {
    display: flex;
    align-items: center;
    gap: 32px;
    padding-top: 32px;
    border-top: 1px solid $border-light;
    
    @media (max-width: $breakpoint-lg) {
      justify-content: center;
    }
    
    @media (max-width: $breakpoint-sm) {
      flex-wrap: wrap;
      gap: 24px;
    }
    
    .trust-item {
      display: flex;
      flex-direction: column;
      
      .trust-number {
        font-size: $text-3xl;
        font-weight: $font-bold;
        color: $primary-green;
        line-height: 1;
      }
      
      .trust-label {
        font-size: $text-sm;
        color: $text-secondary;
        margin-top: 8px;
        white-space: nowrap;
      }
    }
    
    .trust-divider {
      width: 1px;
      height: 48px;
      background: $border-light;
    }
  }
  
  .hero-mockup {
    position: relative;
    
    @media (max-width: $breakpoint-lg) {
      order: 1;
      max-width: 400px;
      margin: 0 auto;
    }
    
    .phone-frame {
      background: #FFFFFF;
      border-radius: $radius-2xl;
      padding: 12px;
      box-shadow: $shadow-xl;
      border: 1px solid $border-light;
      position: relative;
      z-index: 2;
      
      .phone-screen {
        background: #000;
        border-radius: $radius-xl;
        overflow: hidden;
        aspect-ratio: 9 / 19.5;
        
        .app-screenshot {
          width: 100%;
          height: 100%;
          object-fit: cover;
          display: block;
        }
      }
    }
    
    .mockup-glow {
      position: absolute;
      width: 80%;
      height: 60%;
      background: radial-gradient(ellipse, rgba(0, 122, 255, 0.3) 0%, transparent 70%);
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      filter: blur(80px);
      z-index: 1;
    }
  }
}
</style>
