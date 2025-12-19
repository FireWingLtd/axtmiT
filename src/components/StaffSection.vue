<template>
  <section class="staff-team" id="staff">
    <div class="container">
      <div class="section-header-center">
        <span class="pre-title">STAFF TEAM</span>
        <h2 class="section-title">运营团队</h2>
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
      </div>
    </div>
  </section>
</template>

<style scoped>
.staff-team {
    padding: 100px 0;
    background: white;
    text-align: center;
}

.section-header-center {
    margin-bottom: 60px;
}

.pre-title {
    display: block;
    font-size: 14px;
    font-weight: 700;
    color: #f59e0b; /* Orange/Gold color */
    letter-spacing: 2px;
    margin-bottom: 10px;
    text-transform: uppercase;
}

.section-title {
    font-size: 36px;
    color: var(--text-dark);
    margin-bottom: 15px;
    font-weight: 800;
}

.section-subtitle {
    font-size: 14px;
    color: var(--text-light);
    line-height: 1.6;
}

.staff-grid {
    display: flex;
    justify-content: center;
    gap: 60px;
    flex-wrap: wrap;
}

.staff-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 200px;
}

.staff-image-wrapper {
    height: 200px;
    width: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    margin-bottom: 20px;
    transition: transform 0.3s ease;
    /* Add perspective for 3D effect if needed, but user said they will put pictures */
    perspective: 1000px; 
}

.staff-image-placeholder {
    /* This container can be used to apply transforms if the user wants CSS-based oblique */
    /* For now, we keep it simple as the user will provide images */
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
}

.staff-card:hover .staff-image-wrapper {
    transform: translateY(-10px);
}

.staff-image {
    height: 100%;
    object-fit: contain;
    filter: drop-shadow(0 10px 15px rgba(0,0,0,0.1));
    /* If the user uploads oblique images, they will just fit here */
}

.staff-info h3 {
    font-size: 18px;
    font-weight: 700;
    color: var(--text-dark);
    margin-bottom: 5px;
}

.staff-role {
    font-size: 14px;
    color: var(--text-light);
    margin-bottom: 5px;
}

.staff-date {
    font-size: 12px;
    color: #9ca3af;
}

@media (max-width: 768px) {
    .staff-grid {
        gap: 40px;
    }
}
</style>
