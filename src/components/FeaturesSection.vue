<template>
  <section class="features" id="features">
    <div class="features-bg-glow"></div>
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">为什么选择 axtmiT？</h2>
        <p class="section-subtitle">不仅仅是服务器，更是冒险的乐园</p>
      </div>
      
      <div class="features-grid">
        <!-- 1. 稳定流畅 (Main Card) -->
        <div class="feature-card main-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🎯</span>
          </div>
          <div class="text-content">
            <h3>稳定流畅，长久相伴</h3>
            <p>我们拥有经验丰富的管理团队，时刻在线维护游戏环境，确保每位玩家都能享受流畅无忧的生存旅程。</p>
            <div class="tags">
              <span class="tag">高性能服务器</span>
              <span class="tag">专业运维</span>
              <span class="tag">低延迟</span>
            </div>
          </div>
        </div>

        <!-- 2. 聆听声音 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">👂</span>
          </div>
          <div class="text-content">
            <h3>我们聆听每一份声音</h3>
            <p>管理团队用心倾听社区建议，并持续优化游戏内容与体验。</p>
          </div>
        </div>

        <!-- 3. 丰富原版 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🧩</span>
          </div>
          <div class="text-content">
            <h3>丰富原版，创意延伸</h3>
            <p>在纯粹生存的乐趣之上，我们精心搭配了多种拓展玩法模块。</p>
          </div>
        </div>

        <!-- 4. 资产安全 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🛡️</span>
          </div>
          <div class="text-content">
            <h3>资产安全，放心建造</h3>
            <p>完善的领地保护、定期数据备份与反作弊机制，守护你的每一份努力、每一处创造。</p>
          </div>
        </div>

        <!-- 5. 友好社群 -->
        <div class="feature-card">
          <div class="feature-icon-wrapper">
            <span class="feature-icon">🤝</span>
          </div>
          <div class="text-content">
            <h3>友好社群，共建家园</h3>
            <p>这里没有复杂的规则，只有一起探索、建造与分享的日常。</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
    padding: 160px 0;
    background-color: var(--bg-page);
    position: relative;
    overflow: hidden;
}

.features-bg-glow {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 1000px;
    height: 1000px;
    background: radial-gradient(circle, rgba(37, 99, 235, 0.05) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
}

.container {
    position: relative;
    z-index: 1;
}

.section-header {
    text-align: center;
    margin-bottom: 64px;
}

.features-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, minmax(280px, auto));
    gap: 32px;
}

.feature-card {
    background: var(--bg-surface);
    padding: 32px;
    border-radius: 32px;
    border: 1px solid var(--border-light);
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    height: 100%;
}

.main-card {
    grid-column: 1;
    grid-row: span 2;
    background: linear-gradient(135deg, var(--bg-surface), var(--bg-page));
    padding: 64px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.main-card .feature-icon-wrapper {
    width: 80px;
    height: 80px;
    border-radius: 24px;
}

.main-card .feature-icon {
    font-size: 40px;
}

.main-card h3 {
    font-size: 32px;
    margin-bottom: 24px;
}

.main-card p {
    font-size: 18px;
    line-height: 1.8;
}

.main-card .text-content {
    height: 100%;
    display: flex;
    flex-direction: column;
}

.main-card p {
    flex-grow: 1;
}

.feature-card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-lg);
    border-color: var(--primary-color);
}

.feature-icon-wrapper {
    width: 64px;
    height: 64px;
    background: var(--bg-page);
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 32px;
    transition: transform 0.3s ease;
}

.feature-card:hover .feature-icon-wrapper {
    transform: scale(1.1) rotate(5deg);
    background: var(--primary-color);
    color: white;
}

.feature-icon {
    font-size: 32px;
}

.feature-card h3 {
    font-size: 22px;
    font-weight: 800;
    margin-bottom: 16px;
    color: var(--text-main);
}

.feature-card p {
    color: var(--text-secondary);
    line-height: 1.8;
    font-size: 16px;
}

.tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 24px;
}

.tag {
    padding: 6px 14px;
    background: var(--border-light);
    border-radius: 100px;
    font-size: 13px;
    color: var(--text-secondary);
    font-weight: 600;
}

@media (max-width: 1024px) {
    .features-grid {
        grid-template-columns: repeat(2, 1fr);
        grid-template-rows: auto;
    }
    
    .main-card {
        grid-column: span 2;
        grid-row: auto;
    }
}

@media (max-width: 640px) {
    .features-grid {
        grid-template-columns: 1fr;
    }
    
    .main-card {
        grid-column: span 1;
    }
    
    .feature-card {
        padding: 24px;
    }
}
</style>
