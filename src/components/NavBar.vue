<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <header class="header">
    <div class="container">
      <div class="navbar">
        <nav class="nav-menu" :class="{ active: isMenuOpen }">
          <a href="https://jq.qq.com/?_wv=1027&k=5L2dtFQG" target="_blank" class="btn btn-primary">加入社区</a>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
    background-color: rgba(255, 255, 255, 0.8);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--glass-border);
    position: sticky;
    top: 0;
    z-index: 100;
    transition: all 0.3s ease;
}

.navbar {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 16px 0;
}

.logo {
    display: flex;
    align-items: center;
    gap: 12px;
    font-weight: 800;
    font-size: 24px;
    color: var(--text-main);
    letter-spacing: -0.03em;
}

.logo-img {
    width: 36px;
    height: 36px;
}

.nav-menu {
    display: flex;
    gap: 32px;
    align-items: center;
}

.nav-link {
    color: var(--text-secondary);
    text-decoration: none;
    font-weight: 500;
    font-size: 15px;
    transition: color 0.2s ease;
    position: relative;
}

.nav-link:hover {
    color: var(--primary-color);
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 2px;
    background-color: var(--primary-color);
    transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    border-radius: 2px;
}

.nav-link:hover::after {
    width: 100%;
}

.menu-toggle {
    display: none;
    flex-direction: column;
    background: none;
    border: none;
    cursor: pointer;
    gap: 5px;
}

.menu-toggle span {
    width: 25px;
    height: 3px;
    background-color: var(--text-dark);
    border-radius: 2px;
    transition: all 0.3s ease;
}

.menu-toggle.active span:nth-child(1) {
    transform: rotate(45deg) translate(10px, 10px);
}

.menu-toggle.active span:nth-child(2) {
    opacity: 0;
}

.menu-toggle.active span:nth-child(3) {
    transform: rotate(-45deg) translate(7px, -7px);
}

@media (max-width: 768px) {
    .menu-toggle {
        display: flex;
    }

    .nav-menu {
        position: absolute;
        top: 70px;
        left: 0;
        right: 0;
        background-color: white;
        flex-direction: column;
        gap: 20px;
        padding: 20px;
        box-shadow: var(--shadow-sm);
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.3s ease;
    }

    .nav-menu.active {
        max-height: 500px;
    }
}
</style>
