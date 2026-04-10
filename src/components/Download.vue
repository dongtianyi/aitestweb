<template>
  <section id="download" class="download">
    <div class="download-content">
      <h2 class="download-title">开始你的<br/>跑步之旅</h2>
      <p class="download-subtitle">立即下载 Roodle，加入 50,000+ 跑者的行列，用科技提升你的每一步。</p>
      
      <div class="store-buttons">
        <a href="#" class="store-btn">
          <span class="store-btn-icon">🍎</span>
          <div class="store-btn-text">
            <div class="store-btn-label">Download on the</div>
            <div class="store-btn-name">App Store</div>
          </div>
        </a>
        <a href="#" class="store-btn">
          <span class="store-btn-icon">🤖</span>
          <div class="store-btn-text">
            <div class="store-btn-label">GET IT ON</div>
            <div class="store-btn-name">Google Play</div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.download {
  padding: 192px 48px;
  background: $gradient-fire;
  position: relative;
  z-index: 1;
  text-align: center;
  overflow: hidden;
  
  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
    opacity: 0.05;
  }
  
  @media (max-width: $breakpoint-md) {
    padding: 120px 24px;
  }
  
  .download-content {
    position: relative;
    z-index: 10;
    max-width: 800px;
    margin: 0 auto;
  }
  
  .download-title {
    font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
    font-size: clamp(48px, 7vw, 96px);
    font-weight: 700;
    letter-spacing: 0.05em;
    color: $void-black;
    margin-bottom: 24px;
    line-height: 1;
  }
  
  .download-subtitle {
    font-size: 20px;
    color: rgba(5, 5, 7, 0.8);
    margin-bottom: 56px;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
    
    @media (max-width: $breakpoint-sm) {
      font-size: 18px;
    }
  }
  
  .store-buttons {
    display: flex;
    justify-content: center;
    gap: 24px;
    flex-wrap: wrap;
  }
  
  .store-btn {
    display: inline-flex;
    align-items: center;
    gap: 16px;
    padding: 18px 36px;
    background: $void-black;
    color: $pure-white;
    border-radius: 18px;
    text-decoration: none;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    
    &:hover {
      transform: translateY(-6px) scale(1.03);
      box-shadow: 0 25px 50px rgba(0, 0, 0, 0.4);
    }
    
    @media (max-width: $breakpoint-sm) {
      padding: 16px 28px;
      gap: 12px;
    }
    
    .store-btn-icon {
      font-size: 32px;
      
      @media (max-width: $breakpoint-sm) {
        font-size: 28px;
      }
    }
    
    .store-btn-text {
      text-align: left;
    }
    
    .store-btn-label {
      font-family: $font-mono;
      font-size: 10px;
      color: $text-secondary;
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }
    
    .store-btn-name {
      font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
      font-size: 24px;
      font-weight: 700;
      letter-spacing: 0.05em;
      
      @media (max-width: $breakpoint-sm) {
        font-size: 20px;
      }
    }
  }
}
</style>
