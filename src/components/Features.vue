<template>
  <section id="features" class="features">
    <div class="section-container">
      <div class="section-header">
        <p class="section-label">核心功能</p>
        <h2 class="section-title">为什么选择<br/><span class="section-title-highlight">Roodle</span></h2>
      </div>
      
      <div class="features-grid">
        <div class="feature-card" ref="card1">
          <div class="feature-icon">🤖</div>
          <h3 class="feature-title">AI 智能分析</h3>
          <p class="feature-description">基于机器学习的跑步姿态分析，实时监测步频、步幅、着地方式，预防运动损伤，提升跑步效率。</p>
        </div>
        
        <div class="feature-card" ref="card2">
          <div class="feature-icon">📊</div>
          <h3 class="feature-title">数据可视化</h3>
          <p class="feature-description">直观的数据图表，清晰展示训练趋势、心率区间、配速分布，让你对自己的表现一目了然。</p>
        </div>
        
        <div class="feature-card" ref="card3">
          <div class="feature-icon">🎯</div>
          <h3 class="feature-title">个性化训练</h3>
          <p class="feature-description">根据你的目标和水平，AI 生成专属训练计划，从 5K 到全马，科学进阶，稳步提升。</p>
        </div>
        
        <div class="feature-card" ref="card4">
          <div class="feature-icon">🎵</div>
          <h3 class="feature-title">节拍器训练</h3>
          <p class="feature-description">智能节拍器匹配你的目标步频，配合音乐节奏，让训练更有趣，效率更高。</p>
        </div>
        
        <div class="feature-card" ref="card5">
          <div class="feature-icon">👥</div>
          <h3 class="feature-title">社交挑战</h3>
          <p class="feature-description">加入跑团，参与挑战，与好友比拼，让跑步不再孤单，动力满满。</p>
        </div>
        
        <div class="feature-card" ref="card6">
          <div class="feature-icon">🌙</div>
          <h3 class="feature-title">夜间模式</h3>
          <p class="feature-description">精心设计的深色界面，夜间跑步不刺眼，省电更持久。</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const cards = [
  ref<HTMLElement | null>(null),
  ref<HTMLElement | null>(null),
  ref<HTMLElement | null>(null),
  ref<HTMLElement | null>(null),
  ref<HTMLElement | null>(null),
  ref<HTMLElement | null>(null)
]

const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -80px 0px'
}

const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry, index) => {
    if (entry.isIntersecting) {
      setTimeout(() => {
        const el = entry.target as HTMLElement
        el.style.opacity = '1'
        el.style.transform = 'translateY(0)'
      }, index * 100)
      observer.unobserve(entry.target)
    }
  })
}, observerOptions)

onMounted(() => {
  cards.forEach(cardRef => {
    if (cardRef.value) {
      cardRef.value.style.opacity = '0'
      cardRef.value.style.transform = 'translateY(40px)'
      cardRef.value.style.transition = 'all 0.7s cubic-bezier(0.4, 0, 0.2, 1)'
      observer.observe(cardRef.value)
    }
  })
})

onUnmounted(() => {
  observer.disconnect()
})
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.features {
  padding: 192px 48px;
  background: $deep-space;
  position: relative;
  z-index: 1;
  
  @media (max-width: $breakpoint-md) {
    padding: 120px 24px;
  }
  
  .section-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 24px;
    
    @media (max-width: $breakpoint-md) {
      padding: 0;
    }
  }
  
  .section-header {
    text-align: center;
    margin-bottom: 112px;
    
    @media (max-width: $breakpoint-md) {
      margin-bottom: 64px;
    }
    
    .section-label {
      font-family: $font-mono;
      color: $volt-yellow;
      font-size: 13px;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      margin-bottom: 24px;
      display: inline-block;
      padding: 8px 20px;
      background: rgba(255, 230, 0, 0.08);
      border: 1px solid rgba(255, 230, 0, 0.2);
      border-radius: 100px;
    }
    
    .section-title {
      font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
      font-size: clamp(44px, 6vw, 80px);
      font-weight: 700;
      letter-spacing: 0.05em;
      line-height: 1.05;
      color: $text-primary;
      
      .section-title-highlight {
        background: $gradient-fire;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
      }
    }
  }
  
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
    gap: 32px;
    
    @media (max-width: $breakpoint-md) {
      grid-template-columns: 1fr;
      gap: 24px;
    }
  }
  
  .feature-card {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.04) 0%, rgba(255, 255, 255, 0.01) 100%);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 35px;
    padding: 48px;
    position: relative;
    overflow: hidden;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    
    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: $gradient-fire;
      opacity: 0;
      transition: opacity 0.5s ease;
    }
    
    &::after {
      content: '';
      position: absolute;
      top: -50%;
      right: -50%;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle, rgba(255, 230, 0, 0.15) 0%, transparent 70%);
      opacity: 0;
      transition: opacity 0.5s ease;
    }
    
    &:hover {
      transform: translateY(-12px) scale(1.02);
      border-color: rgba(255, 230, 0, 0.4);
      box-shadow: 0 40px 80px rgba(255, 85, 0, 0.3);
      
      &::before {
        opacity: 0.03;
      }
      
      &::after {
        opacity: 1;
      }
      
      .feature-icon {
        transform: rotate(12deg) scale(1.1);
      }
    }
    
    .feature-icon {
      width: 90px;
      height: 90px;
      background: $gradient-fire;
      border-radius: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 48px;
      margin-bottom: 36px;
      position: relative;
      z-index: 1;
      transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .feature-title {
      font-family: 'Bebas Neue', 'Barlow Condensed', 'Noto Sans SC', sans-serif;
      font-size: 28px;
      font-weight: 700;
      letter-spacing: 0.05em;
      margin-bottom: 20px;
      position: relative;
      z-index: 1;
      color: $text-primary;
    }
    
    .feature-description {
      font-family: 'Barlow', 'Noto Sans SC', sans-serif;
      color: $text-secondary;
      font-size: 16px;
      font-weight: 400;
      line-height: 1.9;
      position: relative;
      z-index: 1;
    }
  }
}
</style>
