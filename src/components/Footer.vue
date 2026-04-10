<template>
  <footer id="about" class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-brand">
          <div class="footer-logo">ROODLE</div>
          <p class="footer-tagline">Made with ❤️ for runners.</p>
        </div>
        
        <div class="footer-copy">
          © 2026 Roodle. All rights reserved.
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.footer {
  padding: 80px 48px;
  background: $void-black;
  border-top: 1px solid $cosmic;
  position: relative;
  z-index: 1;
  
  @media (max-width: $breakpoint-md) {
    padding: 60px 24px;
  }
  
  .footer-container {
    max-width: 1400px;
    margin: 0 auto;
  }
  
  .footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    
    @media (max-width: $breakpoint-md) {
      flex-direction: column;
      gap: 24px;
      text-align: center;
    }
  }
  
  .footer-brand {
    .footer-logo {
      font-family: 'Bebas Neue', 'Noto Sans SC', sans-serif;
      font-size: 28px;
      font-weight: 700;
      letter-spacing: 0.1em;
      background: $gradient-fire;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .footer-tagline {
      color: $text-secondary;
      font-size: 14px;
      margin-top: 8px;
    }
  }
  
  .footer-copy {
    font-family: $font-mono;
    color: $text-secondary;
    font-size: 13px;
    letter-spacing: 0.1em;
  }
}
</style>
