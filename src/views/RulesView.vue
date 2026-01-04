<template>
  <div class="rules-page">
    <section class="page-header">
      <div class="container">
        <router-link to="/" class="back-link">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
          </svg>
          返回首页
        </router-link>
        <h1 class="gradient-text">服务器规定</h1>
        <p class="subtitle">为了维护良好的游戏环境，请每位玩家自觉遵守以下准则</p>
      </div>
    </section>

    <section class="content-section">
      <div class="container">
        <!-- 核心准则 -->
        <div class="section-title">
          <h2>核心行为准则</h2>
          <p>为构建和谐社区，每位成员均需恪守以下基本规范</p>
        </div>
        <div class="bento-grid">
          <div class="bento-item">
            <div class="icon">🤝</div>
            <div class="bento-content">
              <h3>文明社交准则</h3>
              <p>倡导友善互助，严禁任何形式的人身攻击、恶意侮辱、骚扰或歧视性言论。我们相信良好的沟通是社区的基石。</p>
            </div>
          </div>
          <div class="bento-item">
            <div class="icon">🛡️</div>
            <div class="bento-content">
              <h3>公平游戏政策</h3>
              <p>严禁使用任何第三方辅助程序、非法模组（如 X-ray、飞行、加速等）篡改游戏数据。</p>
            </div>
          </div>
          <div class="bento-item">
            <div class="icon">🏗️</div>
            <div class="bento-content">
              <h3>资产保护原则</h3>
              <p>严禁恶意破坏他人建筑或窃取私人财物，禁止滥用管理权限干扰正常游戏秩序。</p>
            </div>
          </div>
          <div class="bento-item">
            <div class="icon">🌍</div>
            <div class="bento-content">
              <h3>言论规范与安全责任</h3>
              <p>尊重社区文化多样性，严禁发布涉及政治敏感、种族歧视、性别歧视等违规内容。同时，玩家负有妥善保管账号信息的义务。因个人疏忽导致的账号失窃或损失，社区概不负责。</p>
            </div>
          </div>
          <div class="bento-item">
            <div class="icon">🚫</div>
            <div class="bento-content">
              <h3>账号独立性</h3>
              <p>严禁账号共享或租借。因账号转借产生的任何违规后果及资产损失，均由原账号所有者承担。</p>
            </div>
          </div>
        </div>

        <!-- 违规与处罚说明 -->
        <div class="detailed-content">
          <div class="punishment-intro">
            <h2>违规界定与处罚条例</h2>
            <div class="intro-cards">
              <div class="intro-card warning">
                <h4>作弊零容忍政策</h4>
                <p>axtmiT Community. 对任何破坏游戏公平性的作弊行为始终保持零容忍立场。</p>
              </div>
              <div class="intro-card warning">
                <h4>责任归属原则</h4>
                <p>账号外借产生的违规记录（如禁言或封禁）将直接作用于账号本身，不予撤销。</p>
              </div>
              <div class="intro-card warning">
                <h4>违规交易管控</h4>
                <p>严禁任何形式的现实金钱交易，一经核实将对交易双方采取严肃处理。</p>
              </div>
            </div>
            
            <div class="definition-grid">
              <div class="def-item">
                <span class="def-tag ban">封禁</span>
                <p>终止违规玩家访问服务器各项服务的强制性措施。</p>
              </div>
              <div class="def-item">
                <span class="def-tag mute">禁言</span>
                <p>限制违规玩家在社区内进行公共或私人通讯的管控措施。</p>
              </div>
              <div class="def-item">
                <span class="def-tag warn">警告</span>
                <p>针对轻微违规行为发出的正式警示，作为后续处罚的参考依据。</p>
              </div>
            </div>
          </div>

          <!-- 处罚等级 -->
          <div class="levels-section">
            <h2>处罚等级与适用情形</h2>
            <div class="levels-list">
              <div class="level-item rank-1">
                <div class="level-header">
                  <span class="level-badge">一级处罚</span>
                  <h4>永久封禁</h4>
                </div>
                <ul>
                  <li>使用外挂、脚本或第三方非法程序严重破坏游戏公平性</li>
                  <li>恶意利用系统漏洞（Bug）获取不正当利益或破坏服务器稳定性</li>
                  <li>从事账号非法交易、盗取他人账号或虚拟资产</li>
                  <li>在社区内外组织、煽动大规模对立、网络暴力或恶意舆论攻击</li>
                </ul>
              </div>

              <div class="level-item rank-2">
                <div class="level-header">
                  <span class="level-badge">二级处罚</span>
                  <h4>永久禁言</h4>
                </div>
                <ul>
                  <li>长期利用刷屏、广告外挂等手段严重干扰公共聊天秩序</li>
                  <li>发布涉及违法、色情、极端暴力等严重违规言论</li>
                  <li>持续性辱骂、人身攻击，经多次警告仍未改正</li>
                  <li>组织或参与恶意舆论煽动，对社区氛围造成恶劣影响</li>
                </ul>
              </div>

              <div class="level-item rank-3">
                <div class="level-header">
                  <span class="level-badge">三级处罚</span>
                  <h4>临时封禁</h4>
                </div>
                <ul>
                  <li>短时间或轻度使用非法辅助程序影响游戏公平性</li>
                  <li>对其他成员进行严重人身攻击、恶意辱骂或持续骚扰</li>
                  <li>传播未经证实的虚假信息，恶意煽动玩家对立情绪</li>
                </ul>
              </div>

              <div class="level-item rank-4">
                <div class="level-header">
                  <span class="level-badge">四级处罚</span>
                  <h4>临时禁言</h4>
                </div>
                <ul>
                  <li>短时刷屏、发布商业广告等干扰正常聊天秩序的行为</li>
                  <li>出现轻微辱骂或不文明言论，影响社区交流氛围</li>
                  <li>发表具有煽动性的不当言论，尚未造成重大实质影响</li>
                </ul>
              </div>

              <div class="level-item rank-5">
                <div class="level-header">
                  <span class="level-badge">五级处罚</span>
                  <h4>正式警告</h4>
                </div>
                <ul>
                  <li>初次出现轻微不当言论或行为</li>
                  <li>因误解规则或无意识造成的轻微违规情形</li>
                  <li>其他尚未构成上述处罚等级的轻度不当行为</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.rules-page {
    padding-top: 100px;
    min-height: 100vh;
    background-color: var(--bg-page);
}

.page-header {
    padding: 80px 0;
    text-align: center;
    position: relative;
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

.section-title {
    text-align: center;
    margin-bottom: 48px;
}

.section-title h2 {
    font-size: 32px;
    margin-bottom: 12px;
}

.section-title p {
    color: var(--text-secondary);
}

.bento-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-bottom: 100px;
}

.bento-item {
    background: var(--bg-surface);
    padding: 32px;
    border-radius: 32px;
    border: 1px solid var(--border-light);
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
}

.bento-item:hover {
    transform: translateY(-5px);
    border-color: var(--primary-color);
    box-shadow: var(--shadow-lg);
}

.bento-item .icon {
    font-size: 40px;
    margin-bottom: 20px;
}

.bento-item h3 {
    font-size: 20px;
    margin-bottom: 12px;
    font-weight: 700;
}

.bento-item p {
    color: var(--text-secondary);
    font-size: 15px;
    line-height: 1.6;
}

.detailed-content {
    max-width: 1000px;
    margin: 0 auto;
}

@media (max-width: 1024px) {
    .bento-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 640px) {
    .bento-grid {
        grid-template-columns: 1fr;
    }
}

.punishment-intro {
    margin-bottom: 80px;
}

.punishment-intro h2 {
    text-align: center;
    font-size: 32px;
    margin-bottom: 40px;
}

.intro-cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-bottom: 48px;
}

.intro-card {
    padding: 24px;
    border-radius: 20px;
    background: var(--bg-surface);
    border-left: 4px solid var(--primary-color);
}

.intro-card.warning {
    border-left-color: #ef4444;
}

.intro-card h4 {
    margin-bottom: 12px;
    color: var(--text-main);
}

.intro-card p {
    font-size: 14px;
    color: var(--text-secondary);
    line-height: 1.5;
}

.definition-grid {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
    padding: 32px;
    background: var(--bg-surface);
    border-radius: 24px;
    border: 1px solid var(--border-light);
}

.def-item {
    display: flex;
    align-items: center;
    gap: 12px;
}

.def-tag {
    padding: 4px 12px;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 700;
    color: white;
}

.def-tag.ban { background: #ef4444; }
.def-tag.mute { background: #f59e0b; }
.def-tag.warn { background: #3b82f6; }

.def-item p {
    font-size: 14px;
    color: var(--text-secondary);
}

.levels-section h2 {
    text-align: center;
    font-size: 32px;
    margin-bottom: 40px;
}

.levels-list {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.level-item {
    background: var(--bg-surface);
    padding: 32px;
    border-radius: 24px;
    border: 1px solid var(--border-light);
}

.level-header {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 20px;
}

.level-badge {
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 800;
    text-transform: uppercase;
}

.rank-1 .level-badge { background: rgba(239, 68, 68, 0.1); color: #ef4444; }
.rank-2 .level-badge { background: rgba(245, 158, 11, 0.1); color: #f59e0b; }
.rank-3 .level-badge { background: rgba(239, 68, 68, 0.05); color: #f87171; }
.rank-4 .level-badge { background: rgba(245, 158, 11, 0.05); color: #fbbf24; }
.rank-5 .level-badge { background: rgba(59, 130, 246, 0.1); color: #3b82f6; }

.level-item h4 {
    font-size: 20px;
}

.level-item ul {
    list-style: none;
    padding-left: 0;
}

.level-item li {
    position: relative;
    padding-left: 24px;
    margin-bottom: 8px;
    color: var(--text-secondary);
    font-size: 15px;
}

.level-item li::before {
    content: "•";
    position: absolute;
    left: 8px;
    color: var(--primary-color);
    font-weight: bold;
}

@media (max-width: 1024px) {
    .info-grid, .intro-cards {
        grid-template-columns: 1fr;
    }
    
    .definition-grid {
        flex-direction: column;
        align-items: flex-start;
        gap: 16px;
    }
}
</style>
