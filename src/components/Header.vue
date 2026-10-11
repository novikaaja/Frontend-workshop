<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMenuOpen = ref(false)

const navLinks = [
  { name: 'Home', href: '#home' },
  { name: 'About', href: '#about' },
  { name: 'Skills', href: '#skills' },
  { name: 'Project', href: '#project' },
  { name: 'Experience', href: '#experience' },
  { name: 'Contact', href: '#contact' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

const toggleMobileMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const handleDownloadCv = () => {
  alert('Download CV clicked')
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header
    class="header"
    :class="{ 'header-scrolled': isScrolled }"
  >
    <div class="header-container">
      <!-- Logo disamping kiri -->
      <a href="#" class="logo">
        NOVIKA
      </a>

      <!-- 6 Menu Navigasi ditengah -->
      <nav class="nav-menu" :class="{ 'is-open': isMenuOpen }">
        <ul class="nav-list">
          <li v-for="link in navLinks" :key="link.name" class="nav-item">
            <a
              :href="link.href"
              class="nav-link"
              @click="isMenuOpen = false"
            >
              {{ link.name }}
            </a>
          </li>
        </ul>
      </nav>

      <!-- Button disamping kanan -->
      <div class="action-wrapper">
        <button
          type="button"
          class="btn-cv"
          @click="handleDownloadCv"
        >
          Download CV
        </button>

        <!-- Toggle menu untuk mobile -->
        <button
          type="button"
          class="menu-toggle"
          aria-label="Toggle Navigation"
          @click="toggleMobileMenu"
        >
          <span class="bar" :class="{ 'bar-open-1': isMenuOpen }"></span>
          <span class="bar" :class="{ 'bar-open-2': isMenuOpen }"></span>
          <span class="bar" :class="{ 'bar-open-3': isMenuOpen }"></span>
        </button>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  /* Transparan pink dengan backdrop filter blur */
  background-color: rgba(255, 182, 193, 0.28);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  border-bottom: 1px solid rgba(255, 105, 180, 0.18);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.header-scrolled {
  background-color: rgba(255, 182, 193, 0.45);
  box-shadow: 0 8px 24px -4px rgba(255, 105, 180, 0.18);
  border-bottom: 1px solid rgba(255, 105, 180, 0.28);
}

.header-container {
  width: 100%;
  padding: 1rem 2.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem;
}

/* Logo NOVIKA pink */
.logo {
  font-size: 1.65rem;
  font-weight: 800;
  letter-spacing: 0.12rem;
  color: #ff3385;
  text-decoration: none;
  background: linear-gradient(135deg, #ff1493, #ff69b4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: transform 0.25s ease, filter 0.25s ease;
  user-select: none;
}

.logo:hover {
  transform: scale(1.04);
  filter: drop-shadow(0 0 10px rgba(255, 20, 147, 0.35));
}

/* Navigasi Menu Tengah */
.nav-menu {
  display: flex;
  align-items: center;
}

.nav-list {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 2rem;
  align-items: center;
}

.nav-item {
  position: relative;
}

.nav-link {
  color: #333333;
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  padding: 0.5rem 0.25rem;
  transition: color 0.25s ease;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #ff2a70, #ff758c);
  transition: width 0.3s ease;
  border-radius: 4px;
}

.nav-link:hover {
  color: #e60067;
}

.nav-link:hover::after {
  width: 100%;
}

/* Bagian Kanan (Button CV & Hamburger) */
.action-wrapper {
  display: flex;
  align-items: center;
  gap: 1rem;
}

/* Tombol Merah ke Pink-an */
.btn-cv {
  border: none;
  outline: none;
  cursor: pointer;
  padding: 0.68rem 1.6rem;
  font-size: 0.95rem;
  font-weight: 600;
  color: #ffffff;
  border-radius: 9999px;
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  box-shadow: 0 4px 14px rgba(230, 0, 57, 0.35);
  transition: transform 0.25s ease, box-shadow 0.25s ease, filter 0.25s ease;
}

.btn-cv:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(230, 0, 57, 0.45);
  filter: brightness(1.05);
}

.btn-cv:active {
  transform: translateY(0);
}

/* Hamburger toggle for mobile screens */
.menu-toggle {
  display: none;
  background: transparent;
  border: none;
  cursor: pointer;
  flex-direction: column;
  justify-content: space-around;
  width: 28px;
  height: 22px;
  padding: 0;
}

.bar {
  width: 100%;
  height: 3px;
  background-color: #e60067;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.bar-open-1 {
  transform: translateY(7px) rotate(45deg);
}
.bar-open-2 {
  opacity: 0;
}
.bar-open-3 {
  transform: translateY(-7px) rotate(-45deg);
}

/* Responsiveness */
@media (max-width: 868px) {
  .menu-toggle {
    display: flex;
  }

  .nav-menu {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background: rgba(255, 235, 240, 0.95);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(255, 105, 180, 0.2);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.08);
    display: none;
    padding: 1.5rem 0;
  }

  .nav-menu.is-open {
    display: flex;
    justify-content: center;
  }

  .nav-list {
    flex-direction: column;
    gap: 1.25rem;
    width: 100%;
    text-align: center;
  }

  .btn-cv {
    padding: 0.55rem 1.2rem;
    font-size: 0.88rem;
  }
}
</style>
