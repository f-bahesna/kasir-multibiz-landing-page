<script setup>
import { ArrowRight, ChevronRight, BarChart3, TrendingUp, ShieldCheck } from 'lucide-vue-next'
</script>

<template>
  <section class="hero">
    <div class="container hero-content">
      <div class="hero-text">
        <div class="badge">
          <span class="badge-dot"></span>
          Solusi #1 Untuk Pengusaha Multi-Cabang
        </div>
        <h1>
          Kelola Banyak Bisnis, <br>
          <span class="text-accent">Satu Dashboard.</span>
        </h1>
        <p class="subtitle">
          Tinggalkan cara lama yang ribet. Pantau stok, penjualan, dan profit semua cabang secara real-time. Lebih hemat waktu, profit maksimal.
        </p>
        <div class="cta-group">
          <a href="#pricing" class="btn btn-primary btn-lg">
            Lihat Harga & Promo <ArrowRight :size="20" class="ml-2" />
          </a>
          <a href="https://wa.me/6282133280057?text=halo%20min%20minta%20demo%20kasir%20multibiz%20ya"  target="_blank" class="btn btn-outline btn-lg">
            Jadwalkan Demo
          </a>
        </div>
        <div class="trust-indicators">
          <div class="trust-item">
            <ShieldCheck :size="18" class="text-success" />
            <span>Data Aman Terenkripsi</span>
          </div>
          <div class="trust-item">
            <TrendingUp :size="18" class="text-accent" />
            <span>Rata-rata Profit Naik 35%</span>
          </div>
        </div>
      </div>

      <div class="hero-visual">
        <div class="visual-container">
          <!-- Network Diagram Image -->
          <div class="diagram-wrapper">
            <img src="@/assets/dashboard-diagram.png" alt="Kasir Multibiz Network Diagram" class="diagram-img" />
            
            <!-- Business Owner Image Overlay (Trust Badge) -->
            <div class="owner-overlay">
              <img src="@/assets/business-owner.png" alt="Happy Business Owner" class="owner-img" />
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Background Decor -->
    <div class="bg-blur blur-1"></div>
    <div class="bg-blur blur-2"></div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  padding-top: calc(var(--header-height) + 4rem);
  padding-bottom: 6rem;
  overflow: visible;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 4rem;
  align-items: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: white;
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--color-primary);
  box-shadow: var(--shadow-sm);
  margin-bottom: 1.5rem;
  border: 1px solid #E2E8F0;
}

.badge-dot {
  width: 8px;
  height: 8px;
  background: var(--color-success);
  border-radius: 50%;
  animation: pulse 2s infinite;
}

h1 {
  font-size: 2.5rem;
  font-weight: 800;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  letter-spacing: -0.02em;
}

.subtitle {
  font-size: 1.125rem;
  color: var(--color-text-muted);
  margin-bottom: 2.5rem;
  max-width: 500px;
  line-height: 1.6;
}

.cta-group {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 3rem;
}

.btn-lg {
  padding: 1rem 2rem;
  font-size: 1.125rem;
}

.ml-2 {
  margin-left: 0.5rem;
}

.trust-indicators {
  display: flex;
  gap: 1.5rem;
  font-size: 0.875rem;
  color: var(--color-text-muted);
  font-weight: 500;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.text-success { color: var(--color-success); }

/* Visual Mockup */
.hero-visual {
  position: relative;
  width: 100%;
  display: flex;
  justify-content: center;
  perspective: 1000px;
}

.visual-container {
  position: relative;
  width: 100%;
  max-width: 550px;
}

.diagram-wrapper {
  position: relative;
  border-radius: var(--radius-xl);
  /* Removed heavy shadow/border as the diagram is cleaner illustration */
  padding: 10px;
  z-index: 10;
  transition: transform 0.3s ease;
  animation: float 6s ease-in-out infinite;
}

.diagram-img {
  width: 100%;
  display: block;
  /* Ensure image looks clean against background */
  filter: drop-shadow(0 10px 25px rgba(59, 130, 246, 0.15));
}

.owner-overlay {
  position: absolute;
  bottom: 0px;
  right: -20px;
  width: 140px;
  height: 140px;
  border-radius: 50%;
  overflow: hidden;
  border: 5px solid white;
  box-shadow: var(--shadow-xl);
  z-index: 20;
  animation: float-slow 7s ease-in-out infinite;
}

.owner-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Background Blobs */
.bg-blur {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  z-index: -1;
  opacity: 0.6;
}

.blur-1 {
  width: 400px;
  height: 400px;
  background: var(--color-accent);
  top: -100px;
  right: -100px;
  opacity: 0.1;
}

.blur-2 {
  width: 300px;
  height: 300px;
  background: var(--color-warning);
  bottom: 0;
  left: -50px;
  opacity: 0.1;
}

@keyframes pulse {
  0% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4); }
  70% { box-shadow: 0 0 0 6px rgba(16, 185, 129, 0); }
  100% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0); }
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@keyframes float-slow {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-15px); }
}

@media (min-width: 768px) {
  .hero-content {
    grid-template-columns: 1.2fr 1fr;
  }
  
  h1 {
    font-size: 3.5rem;
  }
  
  .cta-group {
    flex-direction: row;
  }
}
</style>
