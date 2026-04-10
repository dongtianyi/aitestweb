<template>
  <section class="hero">
    <div class="hero-container">
      <!-- 主内容 -->
      <div class="hero-content">
        <div class="hero-badge fade-in">
          <span class="hero-badge-dot"></span>
          <span>AI 驱动 · 专业分析</span>
        </div>
        
        <h1 class="hero-title fade-in delay-1">
          <span class="hero-title-line1">让每一步</span>
          <span class="hero-title-line2">都有数据</span>
        </h1>
        
        <p class="hero-subtitle fade-in delay-2">
          Roodle 是你的智能跑步教练，用 AI 分析你的每一步，提供专业训练建议，
          帮助你突破极限，跑得更快、更远、更健康。
        </p>
        
        <div class="hero-cta-group fade-in delay-3">
          <a href="#download" class="btn-primary">
            <span>免费下载</span>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
          <a href="#features" class="btn-secondary">了解更多</a>
        </div>
        
        <div class="hero-stats fade-in delay-3">
          <div class="stat-item" ref="stat1">
            <div class="stat-value">{{ animatedStats[0] }}</div>
            <div class="stat-label">活跃用户</div>
          </div>
          <div class="stat-item" ref="stat2">
            <div class="stat-value">{{ animatedStats[1] }}</div>
            <div class="stat-label">累计跑量 KM</div>
          </div>
          <div class="stat-item" ref="stat3">
            <div class="stat-value">{{ animatedStats[2] }}</div>
            <div class="stat-label">App Store 评分</div>
          </div>
        </div>
      </div>
      
      <!-- 手机模型 -->
      <div class="hero-visual">
        <div class="phone-container">
          <div class="phone-mockup">
            <div class="phone-notch"></div>
            <div class="phone-screen">
              <div class="app-interface">
                <div class="app-header">
                  <div class="app-date">2026 年 4 月 10 日 周五</div>
                  <div class="app-user">早安，Runner</div>
                </div>
                <div class="app-main-stat">
                  <div class="app-main-stat-label">今日跑量</div>
                  <div class="app-main-stat-value">5.2<span class="app-main-stat-unit">KM</span></div>
                </div>
                <div class="app-stats-grid">
                  <div class="app-stat-card">
                    <div class="app-stat-icon">⚡</div>
                    <div class="app-stat-value">5'30"</div>
                    <div class="app-stat-label">配速</div>
                  </div>
                  <div class="app-stat-card">
                    <div class="app-stat-icon">🔥</div>
                    <div class="app-stat-value">420</div>
                    <div class="app-stat-label">卡路里</div>
                  </div>
                  <div class="app-stat-card">
                    <div class="app-stat-icon">❤️</div>
                    <div class="app-stat-value">142</div>
                    <div class="app-stat-label">心率</div>
                  </div>
                  <div class="app-stat-card">
                    <div class="app-stat-icon">👟</div>
                    <div class="app-stat-value">180</div>
                    <div class="app-stat-label">步频</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <!-- 漂浮卡片 -->
          <div class="floating-card floating-card-1">
            <div class="floating-card-icon">📈</div>
            <div class="floating-card-value">+23%</div>
            <div class="floating-card-label">配速提升</div>
          </div>
          <div class="floating-card floating-card-2">
            <div class="floating-card-icon">🏆</div>
            <div class="floating-card-value">12</div>
            <div class="floating-card-label">个人纪录</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const stat1 = ref<HTMLElement | null>(null)
const stat2 = ref<HTMLElement | null>(null)
const stat3 = ref<HTMLElement | null>(null)

const animatedStats = ref([50, 1000, 4.9])
const targetStats = [50, 1000, 4.9]
const statSuffixes = ['K+', 'M+', '']

const animateCounter = (index: number, target: number, duration = 2500) => {
  let start = 0
  const increment = target / (duration / 16)
  const timer = setInterval(() => {
    start += increment
    if (start >= target) {
      animatedStats.value[index] = target
      // 稍后添加后缀
      setTimeout(() => {
        animatedStats.value[index] = target + statSuffixes[index] as any
      }, 100)
      clearInterval(timer)
    } else {
      if (target % 1 !== 0) {
        animatedStats.value[index] = parseFloat(start.toFixed(1)) as any
      } else {
        animatedStats.value[index] = Math.floor(start) as any
      }
    }
  }, 16)
}

// 滚动观察器
const observerOptions = {
  threshold: 0.5
}

const statsObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const index = [stat1, stat2, stat3].indexOf(entry.target as any)
      if (index !== -1) {
        animateCounter(index, targetStats[index])
        statsObserver.unobserve(entry.target)
      }
    }
  })
}, observerOptions)

onMounted(() => {
  if (stat1.value) statsObserver.observe(stat1.value)
  if (stat2.value) statsObserver.observe(stat2.value)
  if (stat3.value) statsObserver.observe(stat3.value)
})

onUnmounted(() => {
  statsObserver.disconnect()
})
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 160px 48px 80px;
  position: relative;
  z-index: 1;
  
  @media (max-width: $breakpoint-md) {
    padding: 120px 24px 60px;
  }
  
  .hero-container {
    max-width: 1400px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 80px;
    align-items: center;
    
    @media (max-width: $breakpoint-lg) {
      grid-template-columns: 1fr;
      gap: 60px;
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
    gap: 12px;
    padding: 10px 20px;
    background: rgba(255, 230, 0, 0.08);
    border: 1px solid rgba(255, 230, 0, 0.3);
    border-radius: 100px;
    font-family: $font-mono;
    font-size: 12px;
    color: $volt-yellow;
    margin-bottom: 40px;
    animation: badge-pulse 3s ease-in-out infinite;
    
    .hero-badge-dot {
      width: 8px;
      height: 8px;
      background: $volt-yellow;
      border-radius: 50%;
      animation: dot-blink 1.5s ease-in-out infinite;
    }
  }
  
  .hero-title {
    font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
    font-size: clamp(56px, 9vw, 112px);
    font-weight: 700;
    letter-spacing: 0.05em;
    line-height: 0.9;
    margin-bottom: 32px;
    
    .hero-title-line1 {
      display: block;
      color: $text-primary;
    }
    
    .hero-title-line2 {
      display: block;
      background: $gradient-fire;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      position: relative;
      
      &::after {
        content: '';
        position: absolute;
        bottom: 0.1em;
        left: 0;
        width: 100%;
        height: 0.15em;
        background: $gradient-fire;
        transform: skewX(-20deg);
      }
    }
  }
  
  .hero-subtitle {
    font-size: 20px;
    color: $text-secondary;
    margin-bottom: 48px;
    font-weight: 300;
    max-width: 540px;
    line-height: 1.9;
    
    @media (max-width: $breakpoint-md) {
      font-size: 18px;
      max-width: 100%;
    }
  }
  
  .hero-cta-group {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
    margin-bottom: 64px;
    
    @media (max-width: $breakpoint-sm) {
      flex-direction: column;
      gap: 16px;
    }
    
    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 14px;
      padding: 20px 44px;
      background: $gradient-fire;
      color: $void-black;
      border-radius: 100px;
      font-weight: 700;
      font-size: 16px;
      text-decoration: none;
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
        background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.5), transparent);
        transition: left 0.6s ease;
      }
      
      &:hover::before {
        left: 100%;
      }
      
      &:hover {
        transform: translateY(-4px) scale(1.02);
        box-shadow: 0 25px 50px rgba(255, 85, 0, 0.5);
      }
      
      svg {
        transition: transform $transition-base;
      }
      
      &:hover svg {
        transform: translateX(6px);
      }
    }
    
    .btn-secondary {
      display: inline-flex;
      align-items: center;
      gap: 14px;
      padding: 20px 44px;
      background: transparent;
      color: $text-primary;
      border: 2px solid $starlight;
      border-radius: 100px;
      font-weight: 600;
      font-size: 16px;
      text-decoration: none;
      transition: all $transition-base;
      
      &:hover {
        border-color: $cyber-blue;
        background: rgba(0, 240, 255, 0.08);
        transform: translateY(-2px);
      }
    }
  }
  
  .hero-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    padding-top: 48px;
    border-top: 1px solid $cosmic;
    
    @media (max-width: $breakpoint-sm) {
      grid-template-columns: 1fr;
      gap: 24px;
    }
    
    .stat-item {
      text-align: left;
      
      @media (max-width: $breakpoint-sm) {
        text-align: center;
      }
      
      .stat-value {
        font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
        font-size: 56px;
        font-weight: 700;
        letter-spacing: 0.05em;
        background: $gradient-ice;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        line-height: 1;
      }
      
      .stat-label {
        font-family: $font-mono;
        font-size: 12px;
        color: $text-secondary;
        margin-top: 8px;
        letter-spacing: 0.1em;
        text-transform: uppercase;
      }
    }
  }
  
  .hero-visual {
    @media (max-width: $breakpoint-lg) {
      order: 1;
    }
    
    .phone-container {
      position: relative;
    }
    
    .phone-mockup {
      width: 340px;
      height: 700px;
      background: $gradient-void;
      border-radius: 55px;
      border: 3px solid $starlight;
      position: relative;
      overflow: hidden;
      box-shadow: 
        0 100px 150px rgba(0, 0, 0, 0.6),
        0 0 0 2px rgba(255, 230, 0, 0.15),
        inset 0 0 100px rgba(0, 0, 0, 0.5);
      animation: phone-float 8s ease-in-out infinite;
      
      @media (max-width: $breakpoint-md) {
        width: 300px;
        height: 620px;
      }
    }
    
    .phone-notch {
      position: absolute;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 150px;
      height: 35px;
      background: $void-black;
      border-bottom-left-radius: 20px;
      border-bottom-right-radius: 20px;
      z-index: 20;
    }
    
    .phone-screen {
      height: calc(100% - 50px);
      margin: 25px 12px 12px;
      background: $gradient-void;
      border-radius: 45px;
      overflow: hidden;
      position: relative;
    }
    
    .app-interface {
      padding: 32px 24px;
    }
    
    .app-header {
      margin-bottom: 32px;
      
      .app-date {
        font-family: $font-mono;
        font-size: 11px;
        color: $text-secondary;
        letter-spacing: 0.1em;
        text-transform: uppercase;
        margin-bottom: 8px;
      }
      
      .app-user {
        font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
        font-size: 32px;
        font-weight: 700;
        letter-spacing: 0.05em;
        background: $gradient-fire;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
      }
    }
    
    .app-main-stat {
      background: rgba(255, 230, 0, 0.08);
      border: 1px solid rgba(255, 230, 0, 0.2);
      border-radius: 24px;
      padding: 24px;
      margin-bottom: 24px;
      text-align: center;
      
      .app-main-stat-label {
        font-family: $font-mono;
        font-size: 11px;
        color: $volt-yellow;
        letter-spacing: 0.15em;
        text-transform: uppercase;
        margin-bottom: 12px;
      }
      
      .app-main-stat-value {
        font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
        font-size: 64px;
        font-weight: 700;
        letter-spacing: 0.05em;
        color: $text-primary;
        line-height: 1;
        
        .app-main-stat-unit {
          font-family: $font-mono;
          font-size: 16px;
          color: $text-secondary;
        }
      }
    }
    
    .app-stats-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      
      .app-stat-card {
        background: rgba(255, 255, 255, 0.03);
        border: 1px solid rgba(255, 255, 255, 0.08);
        border-radius: 20px;
        padding: 20px;
        text-align: center;
        
        .app-stat-icon {
          font-size: 24px;
          margin-bottom: 8px;
        }
        
        .app-stat-value {
          font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
          font-size: 24px;
          font-weight: 700;
          letter-spacing: 0.05em;
          color: $text-primary;
        }
        
        .app-stat-label {
          font-family: $font-mono;
          font-size: 10px;
          color: $text-secondary;
          letter-spacing: 0.1em;
          text-transform: uppercase;
          margin-top: 4px;
        }
      }
    }
    
    .floating-card {
      position: absolute;
      background: rgba(20, 20, 30, 0.95);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 20px;
      padding: 20px 24px;
      box-shadow: 0 30px 60px rgba(0, 0, 0, 0.5);
      animation: card-float 7s ease-in-out infinite;
      z-index: 20;
      
      &.floating-card-1 {
        top: 80px;
        right: 30px;
        animation-delay: 0s;
      }
      
      &.floating-card-2 {
        bottom: 180px;
        left: 20px;
        animation-delay: -3.5s;
      }
      
      .floating-card-icon {
        font-size: 28px;
        margin-bottom: 8px;
      }
      
      .floating-card-value {
        font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
        font-size: 32px;
        font-weight: 700;
        letter-spacing: 0.05em;
        background: $gradient-growth;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
      }
      
      .floating-card-label {
        font-family: $font-mono;
        font-size: 10px;
        color: $text-secondary;
        letter-spacing: 0.1em;
        text-transform: uppercase;
      }
    }
  }
}

// 动画
@keyframes badge-pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(255, 230, 0, 0.2); }
  50% { box-shadow: 0 0 0 15px rgba(255, 230, 0, 0); }
}

@keyframes dot-blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

@keyframes phone-float {
  0%, 100% { transform: translateY(0) rotate(-6deg); }
  50% { transform: translateY(-25px) rotate(-4deg); }
}

@keyframes card-float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(2deg); }
}

// 淡入动画
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  animation: fadeInUp 1s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

.delay-1 { animation-delay: 0.15s; }
.delay-2 { animation-delay: 0.3s; }
.delay-3 { animation-delay: 0.45s; }

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
