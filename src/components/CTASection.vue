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
      <h2>准备好加入我们了吗？</h2>
      <p>axtmiT 可以使用 mc.axtmit.org 直接进入。</p>
      <div class="cta-buttons">
        <button class="btn btn-primary btn-lg" @click="copyIP">{{ buttonText }}</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta {
    background: linear-gradient(135deg, var(--primary-color) 0%, #667eea 100%);
    color: white;
    padding: 80px 0;
    text-align: center;
}

.cta h2 {
    font-size: 44px;
    margin-bottom: 15px;
    font-weight: 700;
}

.cta p {
    font-size: 18px;
    margin-bottom: 40px;
    opacity: 0.95;
}

.cta-buttons {
    display: flex;
    gap: 20px;
    justify-content: center;
    flex-wrap: wrap;
}

.cta .btn-primary {
    background-color: #10b981;
    color: white;
    font-weight: 800;
    box-shadow: 0 4px 15px rgba(16, 185, 129, 0.4);
    border: 2px solid #10b981;
}

.cta .btn-primary:hover {
    background-color: #059669;
    border-color: #059669;
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(16, 185, 129, 0.5);
}

.cta .btn-secondary {
    border-color: white;
    color: white;
}

@media (max-width: 768px) {
    .cta h2 {
        font-size: 32px;
    }

    .cta-buttons {
        flex-direction: column;
        align-items: center;
    }

    .cta-buttons .btn {
        width: 100%;
    }
}

@media (max-width: 480px) {
    .cta {
        padding: 60px 0;
    }

    .cta h2 {
        font-size: 26px;
        margin-bottom: 10px;
    }

    .cta p {
        font-size: 16px;
        margin-bottom: 30px;
    }
}
</style>
