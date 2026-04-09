<template>
  <footer id="about" class="footer">
    <div class="footer-container">
      <div class="footer-brand">
        <div class="footer-logo">Roodle</div>
        <p class="footer-slogan">好用的跑步分析 App</p>
        <p class="footer-company">北京北南国信息科技有限公司</p>
      </div>
      
      <div class="footer-links">
        <div class="footer-column">
          <h4>产品</h4>
          <ul>
            <li><a href="#features">功能</a></li>
            <li><a href="#advantages">优势</a></li>
            <li><a href="#download">下载</a></li>
          </ul>
        </div>
        <div class="footer-column">
          <h4>支持</h4>
          <ul>
            <li><a href="#">帮助中心</a></li>
            <li><a href="#">联系我们</a></li>
            <li><a href="#">隐私政策</a></li>
          </ul>
        </div>
        <div class="footer-column">
          <h4>关于</h4>
          <ul>
            <li><a href="#">关于我们</a></li>
            <li><a href="#">加入我们</a></li>
            <li><a href="#">商务合作</a></li>
          </ul>
        </div>
      </div>
    </div>
    
    <div class="footer-bottom">
      <div class="footer-container">
        <p class="copyright">
          © 2026 北京北南国信息科技有限公司
        </p>
        <p class="icp">
          ICP 备案号：京 ICP 备 2024087321 号 -3A
        </p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
</script>

<style scoped lang="scss">
@import '../styles/variables.scss';

.footer {
  background: $bg-primary;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 80px 0 0;
  
  .footer-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
  }
  
  .footer-brand {
    margin-bottom: 60px;
    
    .footer-logo {
      font-size: 32px;
      font-weight: 700;
      color: $primary-green;
      margin-bottom: 12px;
    }
    
    .footer-slogan {
      color: $text-secondary;
      font-size: $text-lg;
      margin-bottom: 8px;
    }
    
    .footer-company {
      color: $text-muted;
      font-size: $text-sm;
    }
  }
  
  .footer-links {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 60px;
    margin-bottom: 60px;
    
    @media (max-width: $breakpoint-md) {
      grid-template-columns: repeat(3, 1fr);
      gap: 40px;
    }
    
    @media (max-width: $breakpoint-sm) {
      grid-template-columns: 1fr;
      gap: 40px;
    }
    
    .footer-column {
      h4 {
        color: $text-primary;
        font-size: $text-lg;
        font-weight: $font-semibold;
        margin-bottom: 20px;
      }
      
      ul {
        list-style: none;
        
        li {
          margin-bottom: 12px;
          
          a {
            color: $text-secondary;
            text-decoration: none;
            font-size: $text-base;
            transition: color 0.3s ease;
            
            &:hover {
              color: $primary-green;
            }
          }
        }
      }
    }
  }
  
  .footer-bottom {
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    padding: 30px 0;
    
    .footer-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      
      @media (max-width: $breakpoint-sm) {
        flex-direction: column;
        gap: 12px;
        text-align: center;
      }
      
      .copyright,
      .icp {
        color: $text-muted;
        font-size: $text-sm;
      }
    }
  }
}
</style>
