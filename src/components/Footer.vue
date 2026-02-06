<script setup>
import { Store, Facebook, Instagram, Twitter } from 'lucide-vue-next'
</script>

<template>
  <footer id="contact" class="footer">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="logo">
            <Store :size="24" color="white" />
            <span>Kasir Multibiz</span>
          </div>
          <p>Solusi kasir terintegrasi untuk bisnis multi-cabang. Kelola stok, karyawan, dan laporan keuangan dalam satu dashboard.</p>
        </div>
        
        <div class="footer-links">
          <h4>Produk</h4>
          <a href="#features">Fitur</a>
          <a href="#pricing">Harga</a>
          <a href="#">Roadmap</a>
        </div>

        <div class="footer-links">
          <h4>Dukungan</h4>
          <a href="#">Pusat Bantuan</a>
          <a href="#">Panduan</a>
          <a href="#">Hubungi Kami</a>
        </div>

        <div class="footer-links">
          <h4>Legal</h4>
          <a href="#">Kebijakan Privasi</a>
          <a href="#">Syarat & Ketentuan</a>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; 2024 Kasir Multibiz. All rights reserved.</p>
        <div class="socials">
          <a href="#"><Instagram :size="20" /></a>
          <a href="#"><Facebook :size="20" /></a>
          <a href="#"><Twitter :size="20" /></a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--color-primary);
  color: white;
  padding: 5rem 0 2rem;
}

.footer-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
  margin-bottom: 4rem;
}

.footer-brand p {
  color: var(--color-secondary);
  margin-top: 1rem;
  max-width: 300px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-weight: 700;
  font-size: 1.25rem;
}

.footer-links h4 {
  margin-bottom: 1.5rem;
  font-size: 1rem;
  color: white;
}

.footer-links a {
  display: block;
  color: var(--color-secondary);
  margin-bottom: 0.75rem;
  transition: color 0.2s;
}

.footer-links a:hover {
  color: white;
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  color: var(--color-secondary);
  font-size: 0.875rem;
}

.socials {
  display: flex;
  gap: 1.5rem;
}

.socials a {
  color: var(--color-secondary);
}

.socials a:hover {
  color: white;
}

@media (min-width: 768px) {
  .footer-grid {
    grid-template-columns: 2fr 1fr 1fr 1fr;
  }
  
  .footer-bottom {
    flex-direction: row;
    justify-content: space-between;
  }
}
</style>
