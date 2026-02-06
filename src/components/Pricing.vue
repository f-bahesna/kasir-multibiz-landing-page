<script setup>
import { Check, Calendar } from 'lucide-vue-next'

const tiers = [
  {
    name: 'Paket 3 Bisnis',
    price: 'Rp 25.000.000',
    originalPrice: 'Rp 35.000.000',
    description: 'Ideal untuk pengusaha yang mulai ekspansi.',
    features: [
      'Hingga 3 Cabang Bisnis',
      'Unlimited Transaksi',
      'Laporan Keuangan Dasar',
      'Support Prioritas',
      'Cicilan 3x Bunga 0%'
    ],
    cta: 'Hubungi untuk Diskon',
    highlight: false
  },
  {
    name: 'Paket 5 Bisnis',
    price: 'Rp 30.000.000',
    originalPrice: 'Rp 45.000.000',
    description: 'Best seller untuk pemilik franchise.',
    features: [
      'Hingga 5 Cabang Bisnis',
      'Semua Fitur Paket 3 Bisnis',
      'Advanced Analytics & Forecast',
      'Manajemen Stok Antar Cabang',
      'Cicilan 3x Bunga 0%'
    ],
    cta: 'Hubungi untuk Diskon',
    highlight: true,
    tag: 'Paling Populer'
  }
]
</script>

<template>
  <section id="pricing" class="section bg-light">
    <div class="container">
      <div class="section-header text-center">
        <h2 class="section-title">Investasi Cerdas Untuk Bisnis Anda</h2>
        <p class="section-subtitle">Pilih paket sesuai skala bisnis Anda, tanpa biaya tersembunyi.</p>
      </div>

      <div class="pricing-grid">
        <!-- Defined Tiers -->
        <div 
          v-for="(tier, index) in tiers" 
          :key="index" 
          class="pricing-card mt-12"
          :class="{ 'featured': tier.highlight }"
        >
          <div v-if="tier.highlight" class="popular-tag">{{ tier.tag }}</div>
          <div class="card-header">
            <h3>{{ tier.name }}</h3>
            <div class="price-container">
              <span class="original-price" v-if="tier.originalPrice">{{ tier.originalPrice }}</span>
              <div class="price">{{ tier.price }}</div>
              <div class="lifetime-badge">Bayar Sekali, Milik Selamanya</div>
            </div>
            <p class="desc">{{ tier.description }}</p>
          </div>
          
          <ul class="features-list">
            <li v-for="(feat, fIdx) in tier.features" :key="fIdx">
              <Check :size="18" class="text-accent check-icon" />
              {{ feat }}
            </li>
          </ul>

          <div class="card-footer">
            <a href="https://wa.me/6282133280057?text=halo%20min%20minta%20diskon%20kasir%20multibiz%20ya" target="_blank" class="btn btn-primary w-full">{{ tier.cta }}</a>
            <p class="installment-text" v-if="tier.name.includes('Bisnis')">
              *Bisa dicicil 3x (Tanpa Bunga)
            </p>
          </div>
        </div>

        <!-- Custom/Enterprise Tier -->
        <div class="pricing-card enterprise-card">
          <div class="card-header">
            <h3>Custom Enterprise</h3>
            <div class="price">Solusi Custom</div>
            <p class="desc">Untuk >5 bisnis atau kebutuhan spesifik.</p>
          </div>
          
          <div class="enterprise-benefits">
            <div class="benefit-item">
              <strong>Konsultasi Gratis</strong>
              <p>Analisis kebutuhan bisnis Anda oleh ahli kami.</p>
            </div>
            <div class="benefit-item">
              <strong>Kustomisasi Sistem</strong>
              <p>Fitur yang disesuaikan dengan workflow unik Anda.</p>
            </div>
            <div class="benefit-item">
              <strong>Promo Spesial</strong>
              <p>Bundle Tablet/Device untuk kontrak tahunan.</p>
            </div>
          </div>

          <div class="card-footer">
            <a href="https://wa.me/6282133280057?text=mau%20konsul%20kasir%20multibiz%20dulu%20min" target="_blank" class="btn btn-outline w-full">
              <Calendar :size="18" class="mr-2" />
              Jadwalkan Konsultasi Gratis
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.bg-light {
  background-color: #F1F5F9;
}

.section-header {
  margin-bottom: 5rem;
  position: relative;
  z-index: 10;
}

.pricing-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  align-items: flex-start;
  margin-top: 1rem;
}

.pricing-card {
  background: white;
  border-radius: var(--radius-xl);
  padding: 1.5rem;
  border: 1px solid #E2E8F0;
  position: relative;
  transition: transform 0.2s;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.pricing-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-xl);
}

.pricing-card.featured {
  border: 2px solid var(--color-accent);
  box-shadow: var(--shadow-lg);
  transform: scale(1.02);
}

.pricing-card.featured:hover {
  transform: scale(1.02) translateY(-5px);
}

.popular-tag {
  position: absolute;
  top: -12px;
  right: 2rem;
  background: var(--color-accent);
  color: white;
  padding: 0.25rem 1rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 600;
}

.card-header {
  margin-bottom: 1rem;
  text-align: center;
}

.price-container {
  margin: 0.75rem 0;
}

.original-price {
  text-decoration: line-through;
  color: var(--color-text-muted);
  font-size: 0.875rem;
  display: block;
}

.price {
  font-size: 2.5rem;
  font-weight: 800;
  color: var(--color-primary);
}

.desc {
  color: var(--color-text-muted);
}

.features-list {
  margin-bottom: 1.5rem;
  flex: 1;
}

.features-list li {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 0.5rem;
  font-weight: 500;
  font-size: 0.95rem;
}

.check-icon {
  flex-shrink: 0;
}

.card-footer {
  margin-top: auto;
}

.w-full { width: 100%; }

.installment-text {
  font-size: 0.75rem;
  text-align: center;
  color: var(--color-text-muted);
  margin-top: 0.75rem;
}

/* Enterprise Specific */
.enterprise-card {
  background: var(--color-primary);
  color: white;
  border: none;
}

.enterprise-card h3 { color: white; }
.enterprise-card .price { color: white; font-size: 2rem; }
.enterprise-card .desc { color: #94A3B8; }

.enterprise-benefits {
  margin-bottom: 2rem;
}

.benefit-item {
  margin-bottom: 1rem;
  padding: 0.75rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
}

.benefit-item strong {
  display: block;
  color: var(--color-accent);
  margin-bottom: 0.25rem;
}

.benefit-item p {
  font-size: 0.875rem;
  color: #CBD5E1;
}

.mr-2 { margin-right: 0.5rem; }

.btn-outline {
  border-color: rgba(255, 255, 255, 0.2);
  color: white;
}

.btn-outline:hover {
  background: white;
  color: var(--color-primary);
}

@media (min-width: 900px) {
  .pricing-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.lifetime-badge {
  display: inline-block;
  background: #DCFCE7;
  color: #166534;
  font-size: 0.75rem;
  font-weight: 700;
  padding: 0.25rem 0.75rem;
  border-radius: 99px;
  margin-top: 0.5rem;
  letter-spacing: 0.025em;
  text-transform: uppercase;
}
</style>
