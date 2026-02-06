<script setup>
import { Quote } from 'lucide-vue-next'

const testimonials = [
  {
    name: 'Budi Santoso',
    role: 'Pemilik "Kopi Senja Utama" (3 Cabang)',
    image: 'https://ui-avatars.com/api/?name=Budi+Santoso&background=random',
    content: 'Penerapan Kasir Multibiz memberikan dampak signifikan pada efisiensi operasional ketiga cabang kedai kopi kami. Pemantauan stok dan laporan keuangan kini dapat dilakukan secara real-time dan terpusat. Solusi yang sangat profesional untuk eskalasi bisnis.',
    type: 'local'
  },
  {
    name: 'Hendra Tjahjadi',
    role: 'CEO "Glodok Elektronik Maju" (5 Cabang)',
    image: 'https://ui-avatars.com/api/?name=Hendra+T&background=0D9488&color=fff',
    content: 'Saya kelola 5 cabang toko elektronik dengan ribuan SKU dulunya tantangan besar. Dengan Kasir Multibiz, integrasi data berjalan mulus. Sistemnya memberikan transparansi, data aman, dan kontrol penuh yang kami butuhkan untuk bisnis keluarga.',
    type: 'chinese'
  }
]
</script>

<template>
  <section id="testimonials" class="section">
    <div class="container">
      <div class="section-header text-center">
        <h2 class="section-title">Dipercaya Oleh Pelaku Bisnis Indonesia</h2>
        <p class="section-subtitle">Kisah sukses mitra kami dalam mengembangkan jaringan bisnis mereka.</p>
      </div>

      <div class="testimonials-grid">
        <div 
          v-for="(item, index) in testimonials" 
          :key="index" 
          class="testimonial-card"
        >
          <Quote :size="40" class="quote-icon" />
          <p class="content">"{{ item.content }}"</p>
          
          <div class="author">
            <img :src="item.image" :alt="item.name" class="avatar">
            <div>
              <div class="name">{{ item.name }}</div>
              <div class="role">{{ item.role }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.quote-icon {
  color: var(--color-accent);
  opacity: 0.2;
  margin-bottom: 1.5rem;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.testimonial-card {
  background: white;
  padding: 3rem;
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-sm);
  border: 1px solid #F1F5F9;
}

.content {
  font-size: 1.125rem;
  line-height: 1.8;
  color: var(--color-primary-light);
  font-style: italic;
  margin-bottom: 2rem;
}

.author {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 2px solid var(--color-background);
  object-fit: cover;
}

.name {
  font-weight: 700;
  color: var(--color-primary);
}

.role {
  font-size: 0.875rem;
  color: var(--color-text-muted);
}

@media (min-width: 768px) {
  .testimonials-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

.section-header {
  margin-bottom: 5rem;
  position: relative;
  z-index: 10;
}
</style>
