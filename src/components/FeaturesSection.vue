<template>
  <section class="features" id="features">
    <div class="container">
      <h2 class="section-title">为什么选择 axtmiT？</h2>
      <p class="section-subtitle">不仅仅是服务器，更是冒险的乐园</p>
      
      <div class="features-grid">
        <!-- 1. 稳定流畅 -->
        <div class="feature-card span-2">
          <div class="card-content">
            <div class="feature-icon-wrapper">
              <span class="feature-icon">🎯</span>
            </div>
            <h3>稳定流畅，长久相伴</h3>
            <p>我们拥有经验丰富的管理团队，时刻在线维护游戏环境，确保每位玩家都能享受流畅无忧的生存旅程。</p>
          </div>
        </div>

        <!-- 2. 聆听声音 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">👂</span>
          </div>
          <h3>我们聆听每一份声音</h3>
          <p>管理团队用心倾听社区建议，并持续优化游戏内容与体验，让服务器因你而变得更好。</p>
        </div>

        <!-- 3. 丰富原版 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🧩</span>
          </div>
          <h3>丰富原版，创意延伸</h3>
          <p>在纯粹生存的乐趣之上，我们精心搭配了多种拓展玩法模块，为你提供更丰富、更多元的生存选择，让每一次探索都充满新意。</p>
        </div>

        <!-- 4. 资产安全 -->
        <div class="feature-card highlight">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🛡️</span>
          </div>
          <h3>资产安全，放心建造</h3>
          <p>完善的领地保护、定期数据备份与反作弊机制，守护你的每一份努力、每一处创造。</p>
        </div>

        <!-- 5. 友好社群 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🤝</span>
          </div>
          <h3>友好社群，共建家园</h3>
          <p>这里没有复杂的规则，只有一起探索、建造与分享的日常。我们珍视并维护这份和谐友善的社区氛围。</p>
        </div>

        <!-- 6. 便捷服务 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">⚡</span>
          </div>
          <h3>便捷服务，随时访问</h3>
          <p>提供稳定的网络与便捷的入口，让你随时随地，轻松回到这片属于我们的方块世界。</p>
        </div>

        <!-- 7. 欢迎回家 -->
        <div class="feature-card span-2">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">💝</span>
          </div>
          <h3>欢迎回家</h3>
          <p>axtmiT 不仅仅是一个服务器，更是一个等待你加入的大家庭。我们关切每一位玩家的体验，期待与你在这里写下新的故事。</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
    padding: 120px 0;
    background-color: var(--bg-page);
}

.features-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

.feature-card {
    background: var(--bg-surface);
    padding: 32px;
    border-radius: 24px;
    border: 1px solid var(--border-light);
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
}

.feature-card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-lg);
    border-color: var(--primary-color);
}

/* Bento Grid Layout */
.feature-card.span-2 {
    grid-column: span 2;
    background: linear-gradient(145deg, #ffffff, #f8fafc);
}

.feature-card.highlight {
    background: linear-gradient(135deg, var(--primary-color), var(--primary-dark));
    color: white;
    border: none;
}

.feature-card.highlight h3,
.feature-card.highlight p,
.feature-card.highlight li {
    color: white;
}

.feature-card.highlight .feature-icon-wrapper {
    background: rgba(255, 255, 255, 0.2);
}

.feature-icon-wrapper {
    width: 48px;
    height: 48px;
    background: #eff6ff;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
}

.feature-icon {
    font-size: 24px;
}

.feature-card h3 {
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 12px;
    color: var(--text-main);
}

.feature-card p {
    color: var(--text-secondary);
    margin-bottom: 20px;
    line-height: 1.6;
    font-size: 15px;
}

.feature-list {
    list-style: none;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    margin-top: auto;
}

.feature-list.simple {
    grid-template-columns: 1fr;
}

.feature-list li {
    padding: 4px 0;
    color: var(--text-secondary);
    display: flex;
    align-items: center;
    font-size: 14px;
    font-weight: 500;
}

.feature-list li::before {
    content: '';
    width: 6px;
    height: 6px;
    background-color: var(--accent-color);
    border-radius: 50%;
    margin-right: 10px;
}

.tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: auto;
}

.tag {
    padding: 4px 12px;
    background: #f1f5f9;
    border-radius: 20px;
    font-size: 12px;
    color: var(--text-secondary);
    font-weight: 600;
}

@media (max-width: 1024px) {
    .features-grid {
        grid-template-columns: repeat(2, 1fr);
    }
    
    .feature-card.span-2 {
        grid-column: span 2;
    }
}

@media (max-width: 768px) {
    .features-grid {
        grid-template-columns: 1fr;
    }
    
    .feature-card.span-2 {
        grid-column: span 1;
    }
}
</style>
