<template>
  <div class="join-page">
    <section class="page-header">
      <div class="container">
        <router-link to="/" class="back-link">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
          </svg>
          返回首页
        </router-link>
        <h1 class="gradient-text">加入 axtmiT 团队</h1>
        <p class="subtitle">我们诚邀热爱 Minecraft、愿意为社区贡献力量的伙伴加入我们的团队</p>
      </div>
    </section>

    <section class="content-section">
      <div class="container">
        <div class="jobs-list">
          <div class="job-item">
            <div class="job-visual">
              <div class="visual-circle"></div>
              <span class="visual-icon">💻</span>
            </div>
            <div class="job-content">
              <div class="job-header">
                <span class="job-tag">Java开发</span>
                <h3>Java开发</h3>
              </div>
              <p class="job-desc">负责服务器核心架构维护、插件开发与性能优化，保障服务器稳定高效运行。</p>
              <ul class="job-req">
                <li>熟练掌握 Java 开发，了解插件开发流程</li>
                <li>有 Paper 插件开发经验者优先</li>
              </ul>
            </div>
          </div>
          <div class="job-item">
            <div class="job-visual">
              <div class="visual-circle"></div>
              <span class="visual-icon">🤝</span>
            </div>
            <div class="job-content">
              <div class="job-header">
                <span class="job-tag">社区管理</span>
                <h3>社区管理</h3>
              </div>
              <p class="job-desc">负责维护社区环境，处理玩家问题与矛盾，保持社区和谐。定期策划线上活动，激发玩家参与，增强社区凝聚力。</p>
              <ul class="job-req">
                <li>沟通能力较强，有耐心</li>
                <li>拥有较为稳定的在线时间，能及时响应玩家需求</li>
              </ul>
            </div>
          </div>
          <div class="job-item">
            <div class="job-visual">
              <div class="visual-circle"></div>
              <span class="visual-icon">🎨</span>
            </div>
            <div class="job-content">
              <div class="job-header">
                <span class="job-tag">建筑师/美术</span>
                <h3>建筑师/美术</h3>
              </div>
              <p class="job-desc">负责服务器景观场景的建筑设计与搭建。</p>
              <ul class="job-req">
                <li>熟悉 WorldEdit 等建筑工具</li>
                <li>具备视频剪辑或图片制作能力者优先</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="apply-section">
          <div class="apply-card">
            <h2>申请加入</h2>
            <p>如果您对以上职位感兴趣，请将您的个人介绍发送至我们的邮箱：</p>
            <div class="email-box">
              <span class="email-address">hi@axtmit.org</span>
            </div>
            <p class="apply-note">邮件主题格式:  [加入申请]职位 - 游戏ID</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.join-page {
    padding-top: 100px;
    min-height: 100vh;
    background-color: var(--bg-page);
}

.page-header {
    padding: 80px 0;
    text-align: center;
}

.back-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 600;
    margin-bottom: 32px;
    transition: all 0.3s ease;
    padding: 8px 16px;
    border-radius: 12px;
    background: var(--bg-surface);
    border: 1px solid var(--border-light);
}

.back-link:hover {
    transform: translateX(-5px);
    background: var(--primary-color);
    color: white;
}

.page-header h1 {
    font-size: 48px;
    font-weight: 900;
    margin-bottom: 20px;
}

.subtitle {
    font-size: 20px;
    color: var(--text-secondary);
}

.content-section {
    padding: 60px 0 120px;
}

.jobs-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 32px;
    margin-bottom: 120px;
}

.job-item {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 32px;
    padding: 40px;
    border-radius: 32px;
    background: var(--bg-surface);
    border: 1px solid var(--border-light);
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    height: 100%;
}

.job-item:hover {
    transform: translateY(-10px);
    border-color: var(--primary-color);
    box-shadow: var(--shadow-lg);
}

.job-visual {
    width: 100%;
    height: 160px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.visual-circle {
    position: absolute;
    width: 120px;
    height: 120px;
    background: linear-gradient(135deg, var(--primary-color), #60a5fa);
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
    opacity: 0.1;
    animation: morph 8s ease-in-out infinite;
}

@keyframes morph {
    0% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
    50% { border-radius: 70% 30% 30% 70% / 70% 70% 30% 30%; }
    100% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
}

.visual-icon {
    font-size: 48px;
    z-index: 1;
}

.job-content {
    width: 100%;
}

.job-tag {
    display: inline-block;
    padding: 4px 12px;
    background: var(--primary-color);
    color: white;
    border-radius: 100px;
    font-size: 12px;
    font-weight: 700;
    margin-bottom: 16px;
}

.job-content h3 {
    font-size: 24px;
    margin-bottom: 16px;
    font-weight: 800;
}

.job-desc {
    font-size: 15px;
    color: var(--text-secondary);
    line-height: 1.6;
    margin-bottom: 24px;
}

.job-req {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.job-req li {
    position: relative;
    padding-left: 24px;
    font-size: 14px;
    color: var(--text-main);
    line-height: 1.5;
}

.job-req li::before {
    content: "→";
    position: absolute;
    left: 0;
    color: var(--primary-color);
    font-weight: bold;
}

.apply-section {
    max-width: 1000px;
    margin: 0 auto;
}

.apply-card {
    background: linear-gradient(135deg, var(--bg-surface) 0%, var(--bg-page) 100%);
    padding: 60px 40px;
    border-radius: 32px;
    text-align: center;
    border: 1px solid var(--border-light);
    position: relative;
    z-index: 1;
}

.apply-card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: radial-gradient(circle at top right, rgba(37, 99, 235, 0.05), transparent);
    z-index: -1;
}

.apply-card h2 {
    font-size: 32px;
    font-weight: 900;
    margin-bottom: 16px;
}

.apply-card p {
    font-size: 16px;
    color: var(--text-secondary);
    margin-bottom: 32px;
}

.email-box {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 24px;
    margin-bottom: 24px;
}

.email-box .btn {
    padding: 10px 20px;
    font-size: 14px;
    border-radius: 10px;
}

.email-address {
    font-family: 'Fira Code', monospace;
    font-size: 24px;
    font-weight: 800;
    color: var(--primary-color);
    letter-spacing: -0.5px;
}

.apply-note {
    font-size: 16px;
    color: var(--text-secondary);
    opacity: 0.8;
}

@media (max-width: 1024px) {
    .jobs-list {
        grid-template-columns: 1fr;
        gap: 40px;
    }
    
    .job-item {
        padding: 32px;
    }
    
    .email-box {
        flex-direction: column;
        gap: 20px;
    }
    
    .email-address {
        font-size: 24px;
    }
}
</style>
