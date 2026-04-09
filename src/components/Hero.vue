<template>
  <section class="hero">
    <div class="hero-bg-effect">
      <div class="running-trail"></div>
      <div class="green-glow"></div>
    </div>
    
    <div class="hero-container">
      <!-- 主内容 -->
      <div class="hero-content">
        <h1 class="hero-title">
          好用的<span class="highlight">跑步分析</span>App
        </h1>
        <p class="hero-subtitle">
          让每一次跑步都有数据支撑<br/>
          专业分析 · 科学训练 · 突破自我
        </p>
        
        <div class="hero-cta">
          <a href="#download" class="btn-primary">
            <span class="btn-icon">📱</span>
            免费下载
          </a>
          <a href="#features" class="btn-secondary">
            了解更多
            <span class="btn-icon">→</span>
          </a>
        </div>
        
        <!-- 信任标识 -->
        <div class="hero-trust">
          <div class="trust-item">
            <span class="trust-number">10W+</span>
            <span class="trust-label">活跃用户</span>
          </div>
          <div class="trust-item">
            <span class="trust-number">4.9</span>
            <span class="trust-label">App Store 评分</span>
          </div>
          <div class="trust-item">
            <span class="trust-number">50+</span>
            <span class="trust-label">赛事支持</span>
          </div>
        </div>
      </div>
      
      <!-- APP Mockup -->
      <div class="hero-mockup">
        <div class="phone-frame">
          <div class="phone-screen">
            <div class="app-preview">
              <div class="preview-header">数据统计</div>
              <div class="preview-stats">
                <div class="stat">
                  <span class="stat-value">5.2</span>
                  <span class="stat-unit">km</span>
                </div>
                <div class="stat">
                  <span class="stat-value">142</span>
                  <span class="stat-unit">bpm</span>
                </div>
                <div class="stat">
                  <span class="stat-value">28:30</span>
                  <span class="stat-unit">配速</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- 滚动提示 -->
    <div class="scroll-indicator">
      <span>向下滚动</span>
      <div class="scroll-arrow"></div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.hero {
  min-height: 100vh;
  background: $gradient-hero;
  position: relative;
  overflow: hidden;
  padding-top: 72px;
  
  .hero-bg-effect {
    position: absolute;
    inset: 0;
    pointer-events: none;
    
    .running-trail {
      position: absolute;
      width: 100%;
      height: 100%;
      opacity: 0.1;
      background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%237FFF00' fill-opacity='0.4'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
      animation: trailMove 20s linear infinite;
    }
    
    .green-glow {
      position: absolute;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(127, 255, 0, 0.15) 0%, transparent 70%);
      top: -200px;
      right: -200px;
      animation: glowPulse 4s ease-in-out infinite;
    }
  }
  
  .hero-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 80px 24px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    
    @media (max-width: $breakpoint-lg) {
      grid-template-columns: 1fr;
      text-align: center;
    }
  }
  
  .hero-content {
    @media (max-width: $breakpoint-lg) {
      order: 2;
    }
  }
  
  .hero-title {
    font-size: $text-5xl;
    font-weight: $font-bold;
    color: $text-primary;
    margin-bottom: 24px;
    line-height: 1.2;
    
    @media (max-width: $breakpoint-md) {
      font-size: $text-4xl;
    }
    
    .highlight {
      color: $primary-green;
      position: relative;
      
      &::after {
        content: '';
        position: absolute;
        bottom: 4px;
        left: 0;
        width: 100%;
        height: 8px;
        background: rgba(127, 255, 0, 0.3);
        border-radius: 4px;
      }
    }
  }
  
  .hero-subtitle {
    font-size: $text-xl;
    color: $text-secondary;
    line-height: 1.8;
    margin-bottom: 40px;
    
    @media (max-width: $breakpoint-md) {
      font-size: $text-lg;
    }
  }
  
  .hero-cta {
    display: flex;
    gap: 16px;
    margin-bottom: 60px;
    
    @media (max-width: $breakpoint-lg) {
      justify-content: center;
    }
    
    .btn-primary {
      background: $primary-green;
      color: #000;
      padding: 16px 32px;
      border-radius: 12px;
      font-size: $text-lg;
      font-weight: $font-semibold;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s ease;
      
      &:hover {
        transform: translateY(-4px);
        box-shadow: $shadow-glow;
      }
    }
    
    .btn-secondary {
      background: transparent;
      color: $text-primary;
      padding: 16px 32px;
      border-radius: 12px;
      font-size: $text-lg;
      font-weight: $font-medium;
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 8px;
      border: 1px solid rgba(255, 255, 255, 0.3);
      transition: all 0.3s ease;
      
      &:hover {
        border-color: $primary-green;
        color: $primary-green;
      }
    }
  }
  
  .hero-trust {
    display: flex;
    gap: 40px;
    
    @media (max-width: $breakpoint-lg) {
      justify-content: center;
    }
    
    .trust-item {
      display: flex;
      flex-direction: column;
      
      .trust-number {
        font-size: $text-2xl;
        font-weight: $font-bold;
        color: $primary-green;
      }
      
      .trust-label {
        font-size: $text-sm;
        color: $text-muted;
        margin-top: 4px;
      }
    }
  }
  
  .hero-mockup {
    position: relative;
    
    @media (max-width: $breakpoint-lg) {
      order: 1;
      max-width: 400px;
      margin: 0 auto 60px;
    }
    
    .phone-frame {
      background: $bg-elevated;
      border-radius: $radius-2xl;
      padding: 12px;
      box-shadow: $shadow-lg;
      border: 2px solid rgba(255, 255, 255, 0.1);
      
      .phone-screen {
        background: #000;
        border-radius: 28px;
        overflow: hidden;
        aspect-ratio: 9 / 19.5;
        
        .app-preview {
          padding: 40px 24px;
          height: 100%;
          background: linear-gradient(180deg, #0D0D0D 0%, #1A1A1A 100%);
          
          .preview-header {
            font-size: 24px;
            font-weight: 600;
            color: #fff;
            margin-bottom: 40px;
          }
          
          .preview-stats {
            display: flex;
            flex-direction: column;
            gap: 24px;
            
            .stat {
              display: flex;
              align-items: baseline;
              gap: 8px;
              
              .stat-value {
                font-size: 48px;
                font-weight: 700;
                color: $primary-green;
              }
              
              .stat-unit {
                font-size: $text-lg;
                color: $text-secondary;
              }
            }
          }
        }
      }
    }
  }
  
  .scroll-indicator {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    color: $text-muted;
    font-size: $text-sm;
    
    .scroll-arrow {
      width: 24px;
      height: 24px;
      border-right: 2px solid $text-muted;
      border-bottom: 2px solid $text-muted;
      transform: rotate(45deg);
      animation: scrollBounce 2s ease-in-out infinite;
    }
  }
}

// 动画
@keyframes trailMove {
  0% { background-position: 0 0; }
  100% { background-position: 100px 100px; }
}

@keyframes glowPulse {
  0%, 100% { opacity: 0.5; transform: scale(1); }
  50% { opacity: 0.8; transform: scale(1.1); }
}

@keyframes scrollBounce {
  0%, 100% { transform: rotate(45deg) translate(0, 0); }
  50% { transform: rotate(45deg) translate(-5px, -5px); }
}
</style>
