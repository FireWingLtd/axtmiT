<template>
  <footer class="footer" id="contact">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="logo-text">axtmiT Community.</div>
          <p class="footer-desc">axtmiT Team 成立于2021年，是一个拥有资深运营管理经验的 Minecraft 公益社区服。我们致力于为玩家提供最纯粹、最温暖的生存体验。</p>
        </div>

        <div class="footer-links">
          <div class="link-group">
            <h4>快速链接</h4>
            <a href="https://jq.qq.com/?_wv=1027&k=5L2dtFQG" target="_blank">官方 QQ 群</a>
            <router-link to="/join-us">加入我们</router-link>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; 2021 - 2026 axtmiT Community.</p>
        <p class="footer-disclaimer">"Minecraft" 以及 "我的世界" 为美国微软公司的商标。axtmiT 和本网站与美国微软公司之间没有从属关系。</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
    background-color: var(--bg-footer);
    color: var(--footer-text);
    padding: 100px 0 40px;
    transition: all 0.8s ease;
}

.footer-grid {
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    gap: 80px;
    margin-bottom: 60px;
}

.logo-text {
    font-weight: 900;
    font-size: 32px;
    background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 24px;
}

.footer-desc {
    color: var(--footer-text);
    line-height: 1.8;
    font-size: 16px;
    max-width: 480px;
}

.footer-links {
    display: flex;
    flex-direction: column;
    gap: 40px;
    justify-self: end;
    text-align: right;
}

.link-group h4 {
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 24px;
    color: var(--footer-title);
}

.link-group {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.link-group a {
    color: var(--footer-text);
    text-decoration: none;
    transition: all 0.3s ease;
    font-size: 15px;
}

.link-group a:hover {
    color: var(--primary-color);
    transform: translateX(-4px);
}

.footer-bottom {
    padding-top: 40px;
    text-align: center;
}

.footer-bottom p {
    color: var(--text-tertiary);
    font-size: 14px;
    margin-bottom: 8px;
}

.footer-disclaimer {
    font-size: 12px !important;
    opacity: 0.6;
}

@media (max-width: 1024px) {
    .footer-grid {
        grid-template-columns: 1fr;
        gap: 60px;
    }
}

@media (max-width: 768px) {
    .footer {
        padding: 60px 0 30px;
    }
    
    .footer-links {
        grid-template-columns: 1fr;
        gap: 40px;
    }
}
</style>
