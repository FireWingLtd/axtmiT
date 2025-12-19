<template>
  <footer class="footer" id="contact">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-about">
          <p>axtmiT Team 成立于2021年，是一个拥有资深运营管理经验的Minecraft公益社区服。</p>
        </div>

        <div class="footer-nav">
          <div class="nav-row">
            <a href="#">服务器指南</a>
            <span class="separator">|</span>
            <a href="#">玩家社区</a>
          </div>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; 2021 - 2025 axtmiT</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
    background-color: #1a1a1a; /* Darker background for better contrast */
    color: #ffffff;
    padding: 80px 0 30px;
}

.footer-grid {
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    gap: 60px;
    align-items: center;
    margin-bottom: 40px;
    padding-bottom: 40px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-about {
    text-align: left;
}

.footer-about h4 {
    font-size: 20px;
    margin-bottom: 15px;
    font-weight: 700;
    color: #ffffff;
}

.footer-about p {
    color: #cccccc;
    line-height: 1.6;
    margin: 0;
}

.footer-nav {
    display: flex;
    flex-direction: column;
    gap: 15px;
    align-items: flex-end;
}

.nav-row {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
    flex-wrap: wrap;
}

.nav-row a {
    color: #cccccc;
    text-decoration: none;
    transition: color 0.3s ease;
    font-size: 15px;
}

.nav-row a:hover {
    color: var(--primary-color);
}

.separator {
    color: #666;
    font-size: 14px;
}

.footer-bottom {
    text-align: center;
    color: #999999;
    font-size: 14px;
}

.footer-bottom p {
    margin: 5px 0;
}

@media (max-width: 768px) {
    .footer {
        padding: 60px 0 20px;
    }
    
    .footer-grid {
        grid-template-columns: 1fr;
        gap: 30px;
        text-align: center;
    }

    .footer-about {
        text-align: center;
    }

    .footer-nav {
        align-items: center;
    }
}
</style>
