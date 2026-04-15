<template>
  <section id="advantages" class="advantages">
    <div class="section-container">
      <div class="section-header">
        <span class="section-tag">核心优势</span>
        <h2 class="section-title">为什么选择 Roodle</h2>
      </div>
      
      <div class="advantages-grid">
        <div class="advantage-card">
          <div class="card-number">01</div>
          <div class="card-icon">🎯</div>
          <h3>专业数据分析</h3>
          <p>基于运动科学的多维度分析模型</p>
        </div>
        
        <div class="advantage-card">
          <div class="card-number">02</div>
          <div class="card-icon">✨</div>
          <h3>极简操作体验</h3>
          <p>上手即用，无需学习成本</p>
        </div>
        
        <div class="advantage-card">
          <div class="card-number">03</div>
          <div class="card-icon">📱</div>
          <h3>iOS 原生体验</h3>
          <p>流畅动画，极致性能</p>
        </div>
        
        <div class="advantage-card">
          <div class="card-number">04</div>
          <div class="card-icon">🚀</div>
          <h3>持续更新迭代</h3>
          <p>每月新功能，倾听用户声音</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables-stresswatch.scss';

.advantages {
  padding: 60px 0 120px 0;
  background: linear-gradient(180deg, $bg-primary 0%, $bg-secondary 100%);
  position: relative;
  
  .section-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }
  
  .section-header {
    text-align: center;
    margin-bottom: 80px;
    
    .section-tag {
      display: inline-block;
      background: rgba($primary-green, 0.1);
      color: $primary-green;
      padding: 8px 20px;
      border-radius: $radius-full;
      font-size: $text-sm;
      font-weight: $font-semibold;
      margin-bottom: 20px;
    }
    
    .section-title {
      font-size: $text-5xl;
      font-weight: $font-bold;
      color: $text-primary;
      line-height: 1.2;
      
      @media (max-width: $breakpoint-md) {
        font-size: $text-4xl;
      }
    }
  }
  
  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: $spacing-lg;
    
    @media (max-width: $breakpoint-lg) {
      grid-template-columns: repeat(2, 1fr);
    }
    
    @media (max-width: $breakpoint-sm) {
      grid-template-columns: 1fr;
    }
    
    .advantage-card {
      background: linear-gradient(145deg, $bg-elevated 0%, $bg-tertiary 100%);
      border-radius: $radius-2xl;
      padding: 40px 32px;
      border: 2px solid rgba($primary-green, 0.4);
      text-align: center;
      transition: all $transition-base;
      position: relative;
      overflow: hidden;
      
      &:hover {
        transform: translateY(-8px);
        border-color: rgba($primary-green, 0.8);
        box-shadow: 0 12px 40px rgba($primary-green, 0.2);
      }
      
      &::before {
        content: '';
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: radial-gradient(circle, rgba($primary-green, 0.08) 0%, transparent 70%);
        opacity: 0;
        transition: opacity $transition-base;
      }
      
      &:hover::before {
        opacity: 1;
      }
      
      .card-number {
        position: absolute;
        top: 20px;
        right: 24px;
        font-size: 48px;
        font-weight: $font-bold;
        color: rgba($primary-green, 0.15);
        line-height: 1;
      }
      
      .card-icon {
        font-size: 48px;
        margin-bottom: 24px;
        margin-top: 8px;
      }
      
      h3 {
        font-size: $text-xl;
        color: $text-primary;
        margin-bottom: 12px;
        font-weight: $font-semibold;
      }
      
      p {
        color: $text-secondary;
        font-size: $text-base;
        line-height: 1.6;
      }
    }
  }
}
</style>
