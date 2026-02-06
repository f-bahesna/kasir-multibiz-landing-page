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
        <div class="visual-card main-card">
          <!-- Abstract Dashboard UI Mockup -->
          <div class="card-header">
            <div class="card-title">Total Pendapatan (Bulan Ini)</div>
            <div class="card-value">Rp 1.250.000.000</div>
            <div class="card-trend positive">+12.5% vs bulan lalu</div>
          </div>
          <div class="chart-mockup">
            <div class="bar" style="height: 40%"></div>
            <div class="bar" style="height: 60%"></div>
            <div class="bar" style="height: 45%"></div>
            <div class="bar" style="height: 80%"></div>
            <div class="bar active" style="height: 95%"></div>
            <div class="bar" style="height: 70%"></div>
          </div>
        </div>
        
        <div class="visual-card float-card branch-a">
          <div class="branch-icon bg-orange">☕</div>
          <div>
            <div class="branch-name">Kopi Senja - Cabang 1</div>
            <div class="branch-status">Online • Ramai</div>
          </div>
        </div>

        <div class="visual-card float-card branch-b">
          <div class="branch-icon bg-blue">📱</div>
          <div>
            <div class="branch-name">Gadget Store - Pusat</div>
            <div class="branch-status">Online • Normal</div>
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
  overflow: hidden;
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
  height: 400px;
  width: 100%;
}

.visual-card {
  background: white;
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-lg);
  position: absolute;
  border: 1px solid rgba(255, 255, 255, 0.5);
}

.main-card {
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 2rem;
  z-index: 10;
  background: linear-gradient(145deg, #ffffff, #f8fafc);
}

.card-title {
  font-size: 0.875rem;
  color: var(--color-text-muted);
  margin-bottom: 0.5rem;
}

.card-value {
  font-size: 2rem;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}

.card-trend {
  font-size: 0.875rem;
  color: var(--color-success);
  font-weight: 600;
  margin-bottom: 2rem;
}

.chart-mockup {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  height: 150px;
  gap: 1rem;
}

.bar {
  flex: 1;
  background: #E2E8F0;
  border-radius: 4px;
  transition: height 1s ease;
}

.bar.active {
  background: var(--color-accent);
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
}

.float-card {
  padding: 1rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  z-index: 20;
  min-width: 200px;
  animation: float 6s ease-in-out infinite;
}

.branch-a {
  bottom: -20px;
  left: -20px;
  animation-delay: 0s;
}

.branch-b {
  top: -20px;
  right: -20px;
  animation-delay: 3s;
}

.branch-icon {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
}

.bg-orange { background: #fee2e2; color: #ef4444; }
.bg-blue { background: #dbeafe; color: #2563eb; }

.branch-name { font-weight: 600; font-size: 0.875rem; }
.branch-status { font-size: 0.75rem; color: var(--color-text-muted); }

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
