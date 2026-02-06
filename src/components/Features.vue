<script setup>
import { LayoutGrid, TrendingUp, Users, Smartphone, Clock, ShieldCheck } from 'lucide-vue-next'

const features = [
  {
    icon: LayoutGrid,
    title: 'Multi-Bisnis Terpusat',
    desc: 'Kelola puluhan cabang dari satu dashboard. Ganti outlet hanya dengan satu klik tanpa perlu login ulang.'
  },
  {
    icon: TrendingUp,
    title: 'Laporan Real-Time',
    desc: 'Pantau omzet, profit, dan produk terlaris detik ini juga. Data akurat untuk keputusan bisnis yang cepat.'
  },
  {
    icon: Users,
    title: 'Manajemen Pegawai',
    desc: 'Atur hak akses kasir, admin, dan manajer. Pantau kinerja setiap pegawai dengan log aktivitas detail.'
  },
  {
    icon: Smartphone,
    title: 'Akses Dari Mana Saja',
    desc: 'Pantau bisnis Anda dari HP, Tablet, atau Laptop. Cloud-based system yang selalu online 24/7.'
  },
  {
    icon: Clock,
    title: 'Stok Terintegrasi',
    desc: 'Peringatan otomatis saat stok menipis. Transfer stok antar cabang dengan mudah dan tercatat rapi.'
  },
  {
    icon: ShieldCheck,
    title: 'Keamanan Tingkat Tinggi',
    desc: 'Data Anda dienkripsi dengan standar bank. Backup otomatis setiap hari untuk ketenangan pikiran Anda.'
  }
]
</script>

<template>
  <section id="features" class="section">
    <div class="container">
      <div class="section-header text-center">
        <h2 class="section-title">Fitur Premium Untuk Bos Modern</h2>
        <p class="section-subtitle">Semua alat yang Anda butuhkan untuk expansi bisnis tanpa sakit kepala.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
        <div 
          v-for="(feature, index) in features" 
          :key="index" 
          class="feature-card"
        >
          <div class="icon-wrapper">
            <component :is="feature.icon" :size="24" color="white" />
          </div>
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section-header {
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.25rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.section-subtitle {
  color: var(--color-text-muted);
  font-size: 1.125rem;
  max-width: 600px;
  margin: 0 auto;
}

.feature-card {
  background: white;
  padding: 2rem;
  border-radius: var(--radius-xl);
  border: 1px solid #E2E8F0;
  transition: all 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-xl);
  border-color: var(--color-accent);
}

.icon-wrapper {
  width: 48px;
  height: 48px;
  background: var(--color-accent);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
}

h3 {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
}

p {
  color: var(--color-text-muted);
  line-height: 1.6;
}

@media (min-width: 768px) {
  .grid-cols-1 { grid-template-columns: 1fr; }
  .md\:grid-cols-2 { grid-template-columns: repeat(2, 1fr); }
  .lg\:grid-cols-3 { grid-template-columns: repeat(3, 1fr); }
}
</style>
