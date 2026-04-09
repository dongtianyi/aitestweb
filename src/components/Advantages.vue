<template>
  <section id="advantages" class="advantages">
    <div class="section-container">
      <div class="section-header">
        <h2 class="section-title">为什么选择 Roodle</h2>
        <p class="section-subtitle">专业 · 易用 · 可信赖</p>
      </div>
      
      <div class="advantages-grid">
        <div class="advantage-item">
          <div class="advantage-number">01</div>
          <h3>专业数据分析</h3>
          <p>基于运动科学的多维度分析模型</p>
        </div>
        <div class="advantage-item">
          <div class="advantage-number">02</div>
          <h3>极简操作体验</h3>
          <p>上手即用，无需学习成本</p>
        </div>
        <div class="advantage-item">
          <div class="advantage-number">03</div>
          <h3>全平台支持</h3>
          <p>iOS / Android 完美适配</p>
        </div>
        <div class="advantage-item">
          <div class="advantage-number">04</div>
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
@import '../styles/variables.scss';

.advantages {
  padding: 120px 0;
  background: $bg-primary;
  
  .section-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
  }
  
  .section-header {
    text-align: center;
    margin-bottom: 80px;
    
    .section-title {
      font-size: $text-4xl;
      font-weight: $font-bold;
      color: $text-primary;
      margin-bottom: 16px;
    }
    
    .section-subtitle {
      font-size: $text-xl;
      color: $text-secondary;
    }
  }
  
  .advantages-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
    
    @media (max-width: $breakpoint-lg) {
      grid-template-columns: repeat(2, 1fr);
    }
    
    .advantage-item {
      text-align: center;
      
      .advantage-number {
        font-size: 64px;
        font-weight: $font-bold;
        color: rgba(127, 255, 0, 0.2);
        margin-bottom: 16px;
      }
      
      h3 {
        font-size: $text-xl;
        color: $text-primary;
        margin-bottom: 12px;
      }
      
      p {
        color: $text-secondary;
        font-size: $text-base;
      }
    }
  }
}
</style>
