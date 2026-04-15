<template>
  <section id="download" class="download">
    <div class="download-container">
      <div class="download-content">
        <h2 class="download-title">开始你的<br/><span class="text-gradient">数据化训练之旅</span></h2>
        <p class="download-subtitle">现在下载，立即体验专业跑步分析</p>
        
        <div class="download-card">
          <a href="#" class="store-btn">
            <div class="store-icon">
              <svg viewBox="0 0 24 24" fill="currentColor" class="apple-icon">
                <path d="M18.71 19.5c-.83 1.24-1.71 2.45-3.05 2.47-1.34.03-1.77-.79-3.29-.79-1.53 0-2 .77-3.27.82-1.31.05-2.3-1.32-3.14-2.53C4.25 17 2.94 12.45 4.7 9.39c.87-1.52 2.43-2.48 4.12-2.51 1.28-.02 2.5.87 3.29.87.78 0 2.26-1.07 3.81-.91.65.03 2.47.26 3.64 1.98-.09.06-2.17 1.28-2.15 3.81.03 3.02 2.65 4.03 2.68 4.04-.03.07-.42 1.44-1.38 2.83M13 3.5c.73-.83 1.94-.8 1.94-.8.16 1.47-.74 2.96-1.89 3.77-.69.49-1.86.91-1.93.91-.07 0-1.27-.42-1.84-1.26C8.61 5.19 9.07 3.43 13 3.5z"/>
              </svg>
            </div>
            <div class="store-info">
              <span>Download on the</span>
              <strong>App Store</strong>
            </div>
          </a>
          
          <div class="qr-section">
            <div class="qr-code">
              <img src="/qr-code.jpg" alt="下载二维码" class="qr-image" />
            </div>
            <span class="qr-label">扫码下载</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style lang="scss">
@import '../styles/variables-stresswatch.scss';

.download {
  position: relative;
  padding: 120px 0;
  background: linear-gradient(180deg, $bg-primary 0%, $bg-secondary 100%);
  overflow: hidden;
  
  .download-container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }
  
  .download-content {
    text-align: center;
    
    .download-title {
      font-size: $text-4xl;
      font-weight: $font-bold;
      color: $text-primary;
      line-height: 1.2;
      margin-bottom: 16px;
      
      @media (max-width: $breakpoint-md) {
        font-size: $text-3xl;
      }
      
      .text-gradient {
        background: linear-gradient(135deg, $primary-green 0%, #5AC8FA 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
      }
    }
    
    .download-subtitle {
      font-size: $text-xl;
      color: $text-secondary;
      margin-bottom: 48px;
      
      @media (max-width: $breakpoint-sm) {
        font-size: $text-lg;
      }
    }
  }
  
  .download-card {
    background: $bg-secondary;
    border-radius: $radius-2xl;
    padding: 40px;
    box-shadow: $shadow-xl;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 32px;
    
    @media (max-width: $breakpoint-md) {
      padding: 32px;
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 24px;
    }
  }
  
  .store-btn {
    background: $primary-green;
    color: #FFFFFF;
    padding: 16px 32px;
    border-radius: 14px;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 16px;
    transition: all $transition-base;
    min-width: 240px;
    
    &:hover {
      background: darken($primary-green, 10%);
      transform: translateY(-2px);
      box-shadow: 0 8px 24px rgba($primary-green, 0.3);
    }
    
    .store-icon {
      width: 32px;
      height: 32px;
      
      .apple-icon {
        width: 100%;
        height: 100%;
      }
    }
    
    .store-info {
      display: flex;
      flex-direction: column;
      text-align: left;
      
      span {
        font-size: $text-xs;
        opacity: 0.8;
      }
      
      strong {
        font-size: $text-lg;
        font-weight: 700;
      }
    }
  }
  
  .qr-section {
    text-align: center;
    
    .qr-code {
      width: 200px;
      height: 200px;
      margin: 0 auto 16px;
      background: $bg-tertiary;
      border-radius: $radius-md;
      overflow: hidden;
      
      .qr-image {
        width: 100%;
        height: 100%;
        object-fit: contain;
      }
    }
    
    .qr-label {
      font-size: $text-sm;
      color: $text-secondary;
    }
  }
}
</style>
