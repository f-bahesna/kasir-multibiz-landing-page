<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Menu, X, Store } from 'lucide-vue-next'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const checkScroll = () => {
  isScrolled.value = window.scrollY > 20
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

onMounted(() => {
  window.addEventListener('scroll', checkScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', checkScroll)
})
</script>

<template>
  <nav 
    class="navbar" 
    :class="{ 'scrolled': isScrolled }"
  >
    <div class="container navbar-content">
      <div class="logo">
        <div class="logo-icon">
          <Store :size="24" color="white" />
        </div>
        <span class="logo-text">Kasir Multibiz</span>
      </div>

      <!-- Desktop Menu -->
      <div class="desktop-menu">
        <a href="#features" class="nav-link">Fitur Unggulan</a>
        <a href="#pricing" class="nav-link">Harga & Paket</a>
        <a href="#testimonials" class="nav-link">Kata Mereka</a>
        <a href="https://wa.me/6282133280057?text=mau%20konsul%20kasir%20multibiz%20dulu%20min" target="_blank" class="btn btn-primary btn-sm">Konsultasi Gratis</a>
      </div>

      <!-- Mobile Toggle -->
      <button class="mobile-toggle" @click="toggleMobileMenu">
        <Menu v-if="!isMobileMenuOpen" />
        <X v-else />
      </button>
    </div>

    <!-- Mobile Menu -->
    <div class="mobile-menu" :class="{ 'open': isMobileMenuOpen }">
      <a href="#features" @click="toggleMobileMenu">Fitur Unggulan</a>
      <a href="#pricing" @click="toggleMobileMenu">Harga & Paket</a>
      <a href="#testimonials" @click="toggleMobileMenu">Kata Mereka</a>
      <a href="https://wa.me/6282133280057?text=mau%20konsul%20kasir%20multibiz%20dulu%20min" target="_blank" @click="toggleMobileMenu" class="mobile-cta">Konsultasi Gratis</a>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  transition: all 0.3s ease;
  background: transparent;
  padding: 1.5rem 0;
}

.navbar.scrolled {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  padding: 1rem 0;
  box-shadow: var(--shadow-sm);
}

.navbar-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-weight: 700;
  font-size: 1.25rem;
  color: var(--color-primary);
}

.logo-icon {
  background: var(--color-accent);
  padding: 0.5rem;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-text {
  color: var(--color-primary);
}

.nav-link {
  color: var(--color-text-muted);
  font-weight: 500;
  transition: color 0.2s;
}

.nav-link:hover {
  color: var(--color-accent);
}

.desktop-menu {
  display: none;
  align-items: center;
  gap: 2rem;
}

.mobile-toggle {
  display: block;
  background: none;
  border: none;
  cursor: pointer;
  color: var(--color-primary);
}

.mobile-menu {
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  background: white;
  padding: 2rem 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  box-shadow: var(--shadow-md);
  transform: translateY(-20px);
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}

.mobile-menu.open {
  transform: translateY(0);
  opacity: 1;
  visibility: visible;
}

.mobile-cta {
  color: var(--color-accent);
  font-weight: 600;
}

@media (min-width: 768px) {
  .desktop-menu {
    display: flex;
  }
  .mobile-toggle {
    display: none;
  }
  .mobile-menu {
    display: none;
  }
}
</style>
