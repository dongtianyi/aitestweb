<template>
  <footer id="about" class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-brand">
          <div class="footer-logo">Roodle</div>
          <p class="footer-tagline">让每一步都有数据支撑</p>
        </div>
        
        <div class="footer-links">
          <a href="/privacy-policy.html" class="footer-link" target="_blank">隐私政策</a>
          <a href="/privacy-policy.html" class="footer-link" target="_blank">使用条款</a>
          <a href="#" class="footer-link">联系我们</a>
        </div>
        
        <div class="footer-copy">
          © 2026 Roodle. Made with ❤️ for runners.
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
</script>

<style lang="scss">
@import '../styles/variables-stresswatch.scss';

.footer {
  padding: 60px 0;
  background: $bg-secondary;
  border-top: 1px solid $border-light;
  
  .footer-container {
    max-width: 1116px;
    margin: 0 auto;
    padding: 0 24px;
    
    @media (max-width: $breakpoint-md) {
      padding: 0 16px;
    }
  }
  
  .footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 24px;
    
    @media (max-width: $breakpoint-sm) {
      flex-direction: column;
      text-align: center;
    }
  }
  
  .footer-brand {
    .footer-logo {
      font-size: 24px;
      font-weight: 700;
      color: $text-primary;
      letter-spacing: -0.02em;
    }
    
    .footer-tagline {
      font-size: $text-sm;
      color: $text-secondary;
      margin-top: 8px;
    }
  }
  
  .footer-links {
    display: flex;
    gap: 24px;
    
    @media (max-width: $breakpoint-sm) {
      gap: 16px;
    }
    
    .footer-link {
      font-size: $text-sm;
      color: $text-secondary;
      text-decoration: none;
      transition: color $transition-base;
      
      &:hover {
        color: $text-primary;
      }
    }
  }
  
  .footer-copy {
    font-size: $text-xs;
    color: $text-tertiary;
  }
}
</style>
