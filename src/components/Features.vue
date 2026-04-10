<template>
  <section id="features" class="features">
    <div class="section-container">
      <div class="section-header">
        <span class="section-tag">核心功能</span>
        <h2 class="section-title">全方位数据支持<br/>让训练更科学</h2>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <div class="feature-icon">📅</div>
          </div>
          <h3 class="feature-title">训练记录</h3>
          <p class="feature-desc">日历视图直观展示每次训练，月跑量、配速趋势一目了然</p>
          <ul class="feature-list">
            <li><span class="check">✓</span> 日历视图</li>
            <li><span class="check">✓</span> 月跑量统计</li>
            <li><span class="check">✓</span> 配速趋势</li>
          </ul>
        </div>
        
        <div class="feature-card highlight">
          <div class="feature-badge">最受欢迎</div>
          <div class="feature-icon-wrapper">
            <div class="feature-icon">📊</div>
          </div>
          <h3 class="feature-title">数据分析</h3>
          <p class="feature-desc">多维度专业分析，配速/心率/负荷/步频全面洞察</p>
          <ul class="feature-list">
            <li><span class="check">✓</span> 配速分析</li>
            <li><span class="check">✓</span> 心率区间</li>
            <li><span class="check">✓</span> 训练负荷</li>
            <li><span class="check">✓</span> 步频步幅</li>
          </ul>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <div class="feature-icon">🏃</div>
          </div>
          <h3 class="feature-title">赛事管理</h3>
          <p class="feature-desc">赛事报名、倒计时、路线图、行程管理一站式服务</p>
          <ul class="feature-list">
            <li><span class="check">✓</span> 赛事日历</li>
            <li><span class="check">✓</span> 报名提醒</li>
            <li><span class="check">✓</span> 路线图查看</li>
            <li><span class="check">✓</span> 行程规划</li>
          </ul>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <div class="feature-icon">🔄</div>
          </div>
          <h3 class="feature-title">设备同步</h3>
          <p class="feature-desc">无缝连接 Apple Health、Garmin 等主流设备</p>
          <ul class="feature-list">
            <li><span class="check">✓</span> Apple Health</li>
            <li><span class="check">✓</span> Garmin</li>
            <li><span class="check">✓</span> 自动同步</li>
            <li><span class="check">✓</span> 数据整合</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style lang="scss">
@import '../styles/variables-stresswatch.scss';

.features {
  padding: 120px 0;
  background: $bg-primary;
  position: relative;
  
  .section-container {
    max-width: 1116px;
    margin: 0 auto;
    padding: 0 24px;
    
    @media (max-width: $breakpoint-md) {
      padding: 0 16px;
    }
  }
  
  .section-header {
    text-align: center;
    margin-bottom: 64px;
    
    @media (max-width: $breakpoint-md) {
      margin-bottom: 48px;
    }
    
    .section-tag {
      display: inline-block;
      background: rgba(0, 122, 255, 0.1);
      color: $primary-blue;
      padding: 6px 16px;
      border-radius: $radius-full;
      font-size: $text-sm;
      font-weight: $font-medium;
      margin-bottom: 16px;
    }
    
    .section-title {
      font-size: $text-4xl;
      font-weight: $font-bold;
      color: $text-primary;
      line-height: 1.2;
      letter-spacing: -0.02em;
      
      @media (max-width: $breakpoint-md) {
        font-size: $text-3xl;
      }
    }
  }
  
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
    
    @media (max-width: $breakpoint-sm) {
      grid-template-columns: 1fr;
    }
  }
  
  .feature-card {
    background: $bg-secondary;
    border-radius: $radius-lg;
    padding: 32px;
    box-shadow: $shadow-md;
    border: 1px solid $border-light;
    transition: all $transition-base;
    position: relative;
    
    &:hover {
      transform: translateY(-4px);
      box-shadow: $shadow-lg;
    }
    
    &.highlight {
      border: 2px solid $primary-blue;
      
      .feature-badge {
        display: inline-block;
        background: $primary-blue;
        color: #FFFFFF;
        padding: 4px 12px;
        border-radius: $radius-full;
        font-size: $text-xs;
        font-weight: $font-medium;
        margin-bottom: 16px;
      }
    }
    
    .feature-icon-wrapper {
      width: 56px;
      height: 56px;
      background: rgba(0, 122, 255, 0.1);
      border-radius: $radius-md;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 20px;
      
      .feature-icon {
        font-size: 28px;
      }
    }
    
    .feature-title {
      font-size: $text-xl;
      font-weight: $font-semibold;
      color: $text-primary;
      margin-bottom: 12px;
    }
    
    .feature-desc {
      font-size: $text-base;
      color: $text-secondary;
      line-height: 1.5;
      margin-bottom: 16px;
    }
    
    .feature-list {
      list-style: none;
      padding: 0;
      
      li {
        display: flex;
        align-items: center;
        gap: 8px;
        font-size: $text-sm;
        color: $text-secondary;
        margin-bottom: 8px;
        
        .check {
          color: $primary-green;
          font-weight: 700;
        }
      }
    }
  }
}
</style>
