<template>
  <section id="features" class="features">
    <div class="section-container">
      <!-- 章节标题 -->
      <div class="section-header">
        <h2 class="section-title">核心功能</h2>
        <p class="section-subtitle">全方位数据支持，让训练更科学</p>
      </div>
      
      <!-- 功能网格 -->
      <div class="features-grid">
        <!-- 功能卡片 1: 训练记录 -->
        <div class="feature-card">
          <div class="feature-icon">📅</div>
          <h3 class="feature-title">训练记录</h3>
          <p class="feature-desc">日历视图直观展示每次训练，月跑量、配速趋势一目了然</p>
          <ul class="feature-list">
            <li>✓ 日历视图</li>
            <li>✓ 月跑量统计</li>
            <li>✓ 配速趋势</li>
          </ul>
        </div>
        
        <!-- 功能卡片 2: 数据分析 -->
        <div class="feature-card highlight">
          <div class="feature-badge">最受欢迎</div>
          <div class="feature-icon">📊</div>
          <h3 class="feature-title">数据分析</h3>
          <p class="feature-desc">多维度专业分析，配速/心率/负荷/步频全面洞察</p>
          <ul class="feature-list">
            <li>✓ 配速分析</li>
            <li>✓ 心率区间</li>
            <li>✓ 训练负荷</li>
            <li>✓ 步频步幅</li>
          </ul>
        </div>
        
        <!-- 功能卡片 3: 赛事管理 -->
        <div class="feature-card">
          <div class="feature-icon">🏃</div>
          <h3 class="feature-title">赛事管理</h3>
          <p class="feature-desc">赛事报名、倒计时、路线图、行程管理一站式服务</p>
          <ul class="feature-list">
            <li>✓ 赛事日历</li>
            <li>✓ 报名提醒</li>
            <li>✓ 路线图查看</li>
            <li>✓ 行程规划</li>
          </ul>
        </div>
        
        <!-- 功能卡片 4: 设备同步 -->
        <div class="feature-card">
          <div class="feature-icon">🔄</div>
          <h3 class="feature-title">设备同步</h3>
          <p class="feature-desc">无缝连接 Apple Health、Garmin 等主流设备</p>
          <ul class="feature-list">
            <li>✓ Apple Health</li>
            <li>✓ Garmin</li>
            <li>✓ 自动同步</li>
            <li>✓ 数据整合</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.features {
  padding: 120px 0;
  background: $bg-secondary;
  
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
  
  .features-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
    
    @media (max-width: $breakpoint-md) {
      grid-template-columns: 1fr;
    }
    
    .feature-card {
      background: $gradient-card;
      border-radius: $radius-xl;
      padding: 40px;
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.3s ease;
      position: relative;
      
      &:hover {
        transform: translateY(-8px);
        border-color: rgba(127, 255, 0, 0.3);
        box-shadow: $shadow-glow;
      }
      
      &.highlight {
        border-color: rgba(127, 255, 0, 0.5);
        background: linear-gradient(145deg, rgba(127, 255, 0, 0.1) 0%, #1F1F1F 100%);
        
        .feature-badge {
          position: absolute;
          top: 20px;
          right: 20px;
          background: $primary-green;
          color: #000;
          padding: 6px 16px;
          border-radius: 20px;
          font-size: $text-sm;
          font-weight: $font-semibold;
        }
      }
      
      .feature-icon {
        font-size: 48px;
        margin-bottom: 24px;
      }
      
      .feature-title {
        font-size: $text-2xl;
        font-weight: $font-semibold;
        color: $text-primary;
        margin-bottom: 12px;
      }
      
      .feature-desc {
        font-size: $text-base;
        color: $text-secondary;
        line-height: 1.6;
        margin-bottom: 20px;
      }
      
      .feature-list {
        list-style: none;
        padding: 0;
        
        li {
          color: $text-secondary;
          font-size: $text-base;
          margin-bottom: 8px;
        }
      }
    }
  }
}
</style>
