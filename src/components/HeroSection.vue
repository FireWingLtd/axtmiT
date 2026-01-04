<script setup>
import { onMounted, ref } from 'vue'

const displayText = ref('')
const phrases = ['温馨玩家社区', '纯粹生存世界', '无限冒险之旅', 'axtmiT', '零域']
let phraseIndex = 0
let charIndex = 0
let isDeleting = false

const onlinePlayers = ref(0)
const maxPlayers = ref(100)
const isOnline = ref(false)
const serverVersion = ref('1.20.x - 1.21.x')

const fetchServerStatus = async () => {
  try {
    const response = await fetch('https://list.mczfw.com/api/mc.axtmit.org')
    const data = await response.json()
    // mczfw API: p = online, mp = max, version = version
    if (data.p !== null) {
      onlinePlayers.value = data.p
      maxPlayers.value = data.mp || 100
      isOnline.value = true
      if (data.version && data.version !== 'null') {
        serverVersion.value = data.version
      }
    } else {
      isOnline.value = false
    }
  } catch (err) {
    console.error('Failed to fetch server status:', err)
    isOnline.value = false
  }
}

const typeEffect = () => {
  const currentPhrase = phrases[phraseIndex]
  
  if (isDeleting) {
    displayText.value = currentPhrase.substring(0, charIndex - 1)
    charIndex--
  } else {
    displayText.value = currentPhrase.substring(0, charIndex + 1)
    charIndex++
  }

  // 降低打字速度，让过程更从容
  let typeSpeed = isDeleting ? 100 : 350

  if (!isDeleting && charIndex === currentPhrase.length) {
    // 停留时间加长
    typeSpeed = 4000
    isDeleting = true
  } else if (isDeleting && charIndex === 0) {
    isDeleting = false
    // 随机切换下一个文本，且不与当前重复
    let nextIndex
    do {
      nextIndex = Math.floor(Math.random() * phrases.length)
    } while (nextIndex === phraseIndex)
    phraseIndex = nextIndex
    typeSpeed = 800
  }

  setTimeout(typeEffect, typeSpeed)
}

onMounted(() => {
    typeEffect()
    fetchServerStatus()
    // 每分钟刷新一次
    setInterval(fetchServerStatus, 60000)
})
</script>

<template>
  <section class="hero" id="home">
    <div class="hero-bg-pattern"></div>
    <div class="container">
      <div class="hero-content">
        <h1 class="hero-title">
          欢迎来到<br>
          <span class="gradient-text">{{ displayText }}</span><span class="cursor">|</span>
        </h1>
        <p class="hero-subtitle">一个自由、友好、长久相伴的 Minecraft 生存社区。</p>
        <p class="hero-description">
          这里没有复杂的规则，只有一起探索、建造与分享的日常。<br>
          欢迎回家，开启你的慢节奏方块生活。
        </p>
        <div class="hero-buttons">
          <a href="#join" class="btn btn-primary btn-lg">
            <span>立即加入服务器</span>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
          <router-link to="/rules" class="btn btn-secondary btn-lg">服务器规定</router-link>
        </div>
      </div>

      <div class="hero-visual">
        <div class="floating-card stats-card">
          <div class="card-icon" :class="{ 'is-online': isOnline }">👥</div>
          <div class="card-info">
            <span class="label">在线玩家</span>
            <span class="value">{{ isOnline ? `${onlinePlayers} / ${maxPlayers}` : '服务器离线' }}</span>
          </div>
        </div>
        <div class="floating-card version-card">
          <div class="card-icon">🎮</div>
          <div class="card-info">
            <span class="label">游戏版本</span>
            <span class="value">{{ isOnline ? serverVersion : '服务器离线' }}</span>
          </div>
        </div>
        <div class="main-visual-circle"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
    overflow: hidden;
}

.hero-bg-pattern {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: 
        linear-gradient(rgba(37, 99, 235, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(37, 99, 235, 0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    z-index: -1;
    mask-image: radial-gradient(circle at center, black 30%, transparent 100%);
}

.hero .container {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 80px;
    align-items: center;
    position: relative;
}

.hero-visual {
    position: relative;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.main-visual-circle {
    width: 400px;
    height: 400px;
    background: linear-gradient(135deg, var(--primary-color), #60a5fa);
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.15;
    animation: pulse 6s ease-in-out infinite;
}

@keyframes pulse {
    0%, 100% { transform: scale(1); opacity: 0.15; }
    50% { transform: scale(1.2); opacity: 0.25; }
}

.floating-card {
    position: absolute;
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    padding: 24px;
    border-radius: 24px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    display: flex;
    align-items: center;
    gap: 20px;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.05);
    z-index: 2;
    transition: all 0.3s ease;
}

[data-theme="dark"] .floating-card {
    background: rgba(30, 41, 59, 0.7);
    border-color: rgba(255, 255, 255, 0.1);
}

.stats-card {
    top: 10%;
    right: 10%;
    animation: float 5s ease-in-out infinite;
}

.version-card {
    bottom: 20%;
    left: 0;
    animation: float 7s ease-in-out infinite reverse;
}

@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

.card-icon {
    font-size: 32px;
    width: 60px;
    height: 60px;
    background: var(--bg-page);
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.card-icon.is-online::after {
    content: '';
    position: absolute;
    top: 12px;
    right: 12px;
    width: 10px;
    height: 10px;
    background: #10b981;
    border-radius: 50%;
    border: 2px solid var(--bg-surface);
    box-shadow: 0 0 10px rgba(16, 185, 129, 0.5);
}

.card-info {
    display: flex;
    flex-direction: column;
}

.card-info .label {
    font-size: 14px;
    color: var(--text-secondary);
    font-weight: 600;
}

.card-info .value {
    font-size: 20px;
    font-weight: 800;
    color: var(--text-main);
}

.hero-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    text-align: left;
}

.hero-title {
    font-size: 64px;
    font-weight: 900;
    margin-bottom: 20px;
    line-height: 1.1;
    letter-spacing: -0.04em;
    color: var(--text-main);
}

.gradient-text {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--accent-color) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.hero-subtitle {
    font-size: 22px;
    font-weight: 600;
    color: var(--text-main);
    margin-bottom: 16px;
}

.hero-description {
    font-size: 18px;
    color: var(--text-secondary);
    margin-bottom: 48px;
    line-height: 1.8;
    max-width: 540px;
}

.hero-buttons {
    display: flex;
    gap: 20px;
}

.cursor {
  display: inline-block;
  margin-left: 5px;
  color: var(--primary-color);
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

@media (max-width: 768px) {
    .hero-title {
        font-size: 56px;
    }
    
    .hero-subtitle {
        font-size: 22px;
    }
    
    .hero-description {
        font-size: 18px;
    }
}
</style>
