<script setup>
import { ref } from 'vue'

const buttonText = ref('点击复制')

const copyIP = async () => {
  try {
    await navigator.clipboard.writeText('mc.axtmit.org')
    buttonText.value = '已复制！'
    setTimeout(() => {
      buttonText.value = '点击复制'
    }, 2000)
  } catch (err) {
    console.error('Failed to copy: ', err)
  }
}
</script>

<template>
  <section class="cta" id="join">
    <div class="container">
      <div class="cta-content">
        <h2>准备好加入我们了吗？</h2>
        <p>axtmiT 可以使用 mc.axtmit.org 直接进入。</p>
        <div class="cta-buttons">
          <button class="btn btn-white btn-lg" @click="copyIP">
            <span class="btn-icon">📋</span>
            {{ buttonText }}
          </button>
          <a href="https://jq.qq.com/?_wv=1027&k=5L2dtFQG" target="_blank" class="btn btn-outline-white btn-lg">
            加入 QQ 群
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta {
    background: var(--bg-cta);
    color: white;
    padding: 100px 0;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: all 0.8s ease;
}

.cta::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: radial-gradient(circle at 20% 30%, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
    pointer-events: none;
}

.cta-content {
    position: relative;
    z-index: 1;
}

.cta h2 {
    font-size: 48px;
    margin-bottom: 24px;
    font-weight: 800;
    letter-spacing: -0.02em;
}

.cta p {
    font-size: 20px;
    margin-bottom: 48px;
    opacity: 0.9;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
}

.cta-buttons {
    display: flex;
    gap: 20px;
    justify-content: center;
    flex-wrap: wrap;
    align-items: center;
}

.btn-link-white {
    color: white;
    text-decoration: none;
    font-weight: 600;
    font-size: 16px;
    padding: 12px 24px;
    transition: all 0.3s ease;
    opacity: 0.8;
}

.btn-link-white:hover {
    opacity: 1;
    transform: translateX(5px);
}

.btn-white {
    background: white;
    color: var(--primary-color);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.btn-white:hover {
    transform: translateY(-4px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
    background: #f8fafc;
}

.btn-outline-white {
    background: transparent;
    color: white;
    border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-outline-white:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: white;
    transform: translateY(-4px);
}

.btn-icon {
    font-size: 18px;
}

@media (max-width: 768px) {
    .cta h2 {
        font-size: 36px;
    }

    .cta-buttons {
        flex-direction: column;
        align-items: center;
    }

    .cta-buttons .btn {
        width: 100%;
        max-width: 300px;
    }
}

@media (max-width: 480px) {
    .cta {
        padding: 60px 0;
    }

    .cta h2 {
        font-size: 28px;
        margin-bottom: 16px;
    }

    .cta p {
        font-size: 16px;
        margin-bottom: 32px;
    }
}
</style>
