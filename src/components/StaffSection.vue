<template>
  <section class="staff-team" id="staff">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">运营团队</h2>
        <p class="section-subtitle">用心守护每一位玩家的游戏体验</p>
      </div>
      
      <div class="staff-grid">
        <div class="staff-card">
          <div class="staff-image-wrapper">
            <div class="staff-image-placeholder">
              <img src="/assets/JiaoMu.png" alt="JiaoMu" class="staff-image">
            </div>
          </div>
          <div class="staff-info">
            <h3>JiaoMu</h3>
            <p class="staff-role">酵母</p>
          </div>
        </div>

        <div class="staff-card">
          <div class="staff-image-wrapper">
            <div class="staff-image-placeholder">
              <img src="/assets/TheGuSheng.png" alt="TheGuSheng" class="staff-image">
            </div>
          </div>
          <div class="staff-info">
            <h3>TheGuSheng</h3>
            <p class="staff-role">顾笙</p>
          </div>
        </div>

        <div class="staff-card">
          <div class="staff-image-wrapper">
            <div class="staff-image-placeholder">
              <img src="/assets/Thejiangbaij.png" alt="Thejiangbaij" class="staff-image">
            </div>
          </div>
          <div class="staff-info">
            <h3>Thejiangbaij</h3>
            <p class="staff-role">江佰</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.staff-team {
    padding: 120px 0;
    background: var(--bg-surface);
    text-align: center;
}

.section-header {
    margin-bottom: 80px;
}

.pre-title {
    display: block;
    font-size: 14px;
    font-weight: 800;
    color: var(--primary-color);
    letter-spacing: 3px;
    margin-bottom: 12px;
    text-transform: uppercase;
}

.section-subtitle {
    color: var(--text-secondary);
    font-size: 18px;
    margin-top: 16px;
}

.staff-grid {
    display: flex;
    justify-content: center;
    gap: 80px;
    flex-wrap: wrap;
}

.staff-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 240px;
    transition: all 0.3s ease;
}

.staff-image-wrapper {
    height: 240px;
    width: 240px;
    background: transparent;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    margin-bottom: 24px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
}

.staff-card:hover .staff-image-wrapper {
    transform: translateY(-12px);
}

.staff-image-placeholder {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
}

.staff-image {
    height: 90%;
    object-fit: contain;
    filter: drop-shadow(0 10px 20px rgba(0,0,0,0.1));
    transition: transform 0.4s ease;
}

.staff-card:hover .staff-image {
    transform: scale(1.05);
}

.staff-info h3 {
    font-size: 22px;
    font-weight: 800;
    color: var(--text-main);
    margin-bottom: 4px;
}

.staff-role {
    font-size: 16px;
    color: var(--text-secondary);
    margin-bottom: 12px;
}
0
@media (max-width: 768px) {
    .staff-grid {
        gap: 48px;
    }
    
    .staff-card {
        width: 200px;
    }
    
    .staff-image-wrapper {
        width: 200px;
        height: 200px;
    }
}
</style>
