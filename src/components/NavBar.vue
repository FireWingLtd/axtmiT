<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

const toggleTheme = () => {
  isDark.value = !isDark.value
  document.documentElement.setAttribute('data-theme', isDark.value ? 'dark' : 'light')
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light')
}

onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme === 'dark' || (!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDark.value = true
    document.documentElement.setAttribute('data-theme', 'dark')
  }
})
</script>

<template>
  <button class="theme-toggle-float" @click="toggleTheme" :aria-label="isDark ? '切换到亮色模式' : '切换到暗色模式'">
    <div class="icon-wrapper" :class="{ 'is-dark': isDark }">
      <svg class="sun-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="5"></circle>
        <line x1="12" y1="1" x2="12" y2="3"></line>
        <line x1="12" y1="21" x2="12" y2="23"></line>
        <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
        <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
        <line x1="1" y1="12" x2="3" y2="12"></line>
        <line x1="21" y1="12" x2="23" y2="12"></line>
        <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
        <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
      </svg>
      <svg class="moon-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
      </svg>
    </div>
  </button>
</template>

<style scoped>
.theme-toggle-float {
    position: fixed;
    top: 24px;
    right: 24px;
    z-index: 1001;
    width: 44px;
    height: 44px;
    background: transparent;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: hidden;
}

.theme-toggle-float:hover {
    transform: translateY(-2px) rotate(8deg);
}

.icon-wrapper {
    position: relative;
    width: 24px;
    height: 24px;
    transition: transform 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.icon-wrapper.is-dark {
    transform: rotate(360deg);
}

.sun-icon, .moon-icon {
    position: absolute;
    top: 0;
    left: 0;
    width: 24px;
    height: 24px;
    transition: all 0.4s ease;
}

.sun-icon {
    color: #f59e0b;
    opacity: 1;
    transform: scale(1);
}

.is-dark .sun-icon {
    opacity: 0;
    transform: scale(0) rotate(-45deg);
}

.moon-icon {
    color: #6366f1;
    opacity: 0;
    transform: scale(0) rotate(45deg);
}

.is-dark .moon-icon {
    opacity: 1;
    transform: scale(1) rotate(0);
}
</style>
