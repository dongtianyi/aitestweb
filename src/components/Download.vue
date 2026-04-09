<template>
  <section id="download" class="download">
    <div class="download-container">
      <h2 class="download-title">开始你的数据化训练之旅</h2>
      <p class="download-subtitle">现在下载，立即体验专业跑步分析</p>
      
      <div class="download-buttons">
        <a href="#" class="store-btn">
          <div class="store-icon">🍎</div>
          <div class="store-info">
            <span>Download on the</span>
            <strong>App Store</strong>
          </div>
        </a>
        
        <a href="#" class="store-btn">
          <div class="store-icon">▶️</div>
          <div class="store-info">
            <span>GET IT ON</span>
            <strong>Google Play</strong>
          </div>
        </a>
      </div>
      
      <div class="download-qr">
        <div class="qr-placeholder">
          <span>二维码</span>
        </div>
        <span>扫码下载</span>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.download {
  padding: 120px 0;
  background: linear-gradient(180deg, $bg-secondary 0%, $bg-primary 100%);
  
  .download-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 24px;
    text-align: center;
  }
  
  .download-title {
    font-size: $text-4xl;
    font-weight: $font-bold;
    color: $text-primary;
    margin-bottom: 16px;
  }
  
  .download-subtitle {
    font-size: $text-xl;
    color: $text-secondary;
    margin-bottom: 60px;
  }
  
  .download-buttons {
    display: flex;
    justify-content: center;
    gap: 24px;
    margin-bottom: 60px;
    
    @media (max-width: $breakpoint-sm) {
      flex-direction: column;
      align-items: center;
    }
    
    .store-btn {
      background: $bg-elevated;
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 12px;
      padding: 12px 32px;
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
      transition: all 0.3s ease;
      
      &:hover {
        border-color: $primary-green;
        transform: translateY(-4px);
      }
      
      .store-icon {
        font-size: 32px;
      }
      
      .store-info {
        text-align: left;
        
        span {
          display: block;
          font-size: $text-xs;
          color: $text-muted;
        }
        
        strong {
          font-size: $text-lg;
          color: $text-primary;
        }
      }
    }
  }
  
  .download-qr {
    display: inline-block;
    
    .qr-placeholder {
      width: 200px;
      height: 200px;
      background: $bg-elevated;
      border-radius: 16px;
      border: 2px solid rgba(127, 255, 0, 0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      
      span {
        color: $text-muted;
        font-size: $text-base;
      }
    }
    
    > span {
      display: block;
      margin-top: 16px;
      color: $text-secondary;
      font-size: $text-base;
    }
  }
}
</style>
