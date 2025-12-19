<script setup>
import { onMounted, ref } from 'vue'

const displayText = ref('')
const phrases = ['纯粹生存世界', '温馨玩家社区', '无限冒险之旅']
let phraseIndex = 0
let charIndex = 0
let isDeleting = false

const typeEffect = () => {
  const currentPhrase = phrases[phraseIndex]
  
  if (isDeleting) {
    displayText.value = currentPhrase.substring(0, charIndex - 1)
    charIndex--
  } else {
    displayText.value = currentPhrase.substring(0, charIndex + 1)
    charIndex++
  }

  let typeSpeed = isDeleting ? 100 : 200

  if (!isDeleting && charIndex === currentPhrase.length) {
    typeSpeed = 2000
    isDeleting = true
  } else if (isDeleting && charIndex === 0) {
    isDeleting = false
    phraseIndex = (phraseIndex + 1) % phrases.length
    typeSpeed = 500
  }

  setTimeout(typeEffect, typeSpeed)
}

onMounted(() => {
    typeEffect()
    const counters = document.querySelectorAll('.stat-number');
    const speed = 200;
    
    const observerCounters = new IntersectionObserver(function(entries) {
        entries.forEach(entry => {
            if (entry.isIntersecting && !entry.target.dataset.animated) {
                const target = entry.target;
                const finalValue = parseInt(target.getAttribute('data-target'));
                target.dataset.animated = 'true';
                
                let current = 0;
                const increment = Math.ceil(finalValue / (speed / 10));
                
                const counter = setInterval(() => {
                    current += increment;
                    if (current >= finalValue) {
                        target.textContent = finalValue + '+';
                        clearInterval(counter);
                    } else {
                        target.textContent = current + '+';
                    }
                }, 10);
            }
        });
    }, { threshold: 0.5 });
    
    counters.forEach(counter => observerCounters.observe(counter));
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
        <p class="hero-subtitle">axtmiT Community.<br>一个自由、友好、长久相伴的 Minecraft 社区服务器。</p>
        <p class="hero-description">
          这里没有复杂的规则，只有一起探索、建造与分享的日常。<br>
          欢迎回家，开启你的慢节奏方块生活。
        </p>
        <div class="hero-buttons">
          <a href="https://jq.qq.com/?_wv=1027&k=5L2dtFQG" target="_blank" class="btn btn-primary btn-lg">
            <span>立即加入服务器</span>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
          </a>
          <a href="#features" class="btn btn-secondary btn-lg">了解更多</a>
        </div>
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
    justify-content: center; /* Reverted to center to align the container */
    padding: 0;
    overflow: hidden;
    scroll-snap-align: start; /* Only snap the hero section */
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
    mask-image: linear-gradient(to bottom, black 40%, transparent 100%);
}

.hero .container {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    min-height: 100vh;
    width: 100%; /* Ensure container takes full width to center properly */
}

.badge {
    display: inline-block;
    padding: 6px 12px;
    background-color: rgba(37, 99, 235, 0.1);
    color: var(--primary-color);
    border-radius: 20px;
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 24px;
    border: 1px solid rgba(37, 99, 235, 0.2);
}

.hero-title {
    font-size: 64px;
    font-weight: 800;
    margin-bottom: 16px;
    line-height: 1.1;
    letter-spacing: -0.03em;
}

.gradient-text {
    background: linear-gradient(135deg, var(--primary-color) 0%, var(--accent-color) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.hero-subtitle {
    font-size: 24px;
    font-weight: 500;
    color: var(--text-secondary);
    margin-bottom: 24px;
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
    gap: 16px;
}

@media (max-width: 1024px) {
    .hero .container {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 40px;
    }

    .hero-description {
        margin-left: auto;
        margin-right: auto;
    }

    .hero-buttons {
        justify-content: center;
    }
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
</style>
