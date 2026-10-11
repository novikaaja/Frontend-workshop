<script setup>
const socialLinks = [
  {
    name: 'Github',
    href: 'https://github.com',
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.53 1.032 1.53 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>`
  },
  {
    name: 'WhatsApp',
    href: 'https://whatsapp.com',
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.301-.15-1.78-.878-2.056-.979-.275-.101-.475-.15-.675.15-.2.3-.775.979-.95 1.179-.175.2-.351.226-.651.075s-1.27-.468-2.42-1.493c-.895-.798-1.5-1.784-1.675-2.084s-.019-.462.131-.611c.135-.134.301-.35.451-.525.15-.175.2-.3.3-.5.1-.2.05-.376-.025-.526s-.675-1.628-.925-2.23c-.244-.585-.492-.506-.675-.515-.175-.009-.375-.01-.575-.01s-.525.075-.8.375c-.275.3-1.05 1.027-1.05 2.505s1.075 2.905 1.225 3.105c.15.2 2.115 3.23 5.124 4.53 3.01 1.3 3.01.868 3.56.818.55-.05 1.78-.727 2.03-1.429.25-.702.25-1.303.175-1.429-.075-.125-.275-.2-.576-.35zM12.04 2C6.54 2 2.08 6.46 2.08 11.96c0 1.97.58 3.81 1.58 5.37L2 22l4.82-1.59a9.92 9.92 0 005.22 1.47h.005c5.5 0 9.96-4.46 9.96-9.96A9.97 9.97 0 0012.04 2z"/></svg>`
  },
  {
    name: 'Instagram',
    href: 'https://instagram.com',
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>`
  },
  {
    name: 'Email',
    href: 'mailto:nopiajalahya@gmail.com',
    icon: `<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>`
  }
]

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <!-- Kolom Kiri -->
      <div class="footer-left">
        <p class="copyright-text">
          &copy; 2026 Portofolio - <span class="author-name">Luriyanti Novika Purnama Sari</span>.
        </p>
      </div>

      <!-- Kolom Kanan (Logo Sosial Media + Tanda Panah ke Atas) -->
      <div class="footer-right">
        <!-- Logo Sosial Media -->
        <div class="footer-socials">
          <a
            v-for="item in socialLinks"
            :key="item.name"
            :href="item.href"
            :title="item.name"
            target="_blank"
            rel="noopener noreferrer"
            class="social-icon"
            v-html="item.icon"
          ></a>
        </div>

        <!-- Tombol Panah ke Atas -->
        <button
          type="button"
          class="btn-back-to-top"
          aria-label="Scroll to Top"
          title="Kembali ke atas"
          @click="scrollToTop"
        >
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
            <polyline points="18 15 12 9 6 15"></polyline>
          </svg>
        </button>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  width: 100%;
  background: rgba(255, 255, 255, 0.85);
  border-top: 1px solid rgba(255, 105, 180, 0.22);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  padding: 1.75rem 2.5rem;
}

.footer-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem;
}

/* Kolom Kiri */
.footer-left {
  display: flex;
  align-items: center;
}

.copyright-text {
  font-size: 0.95rem;
  color: #6b7280;
  line-height: 1.5;
}

.author-name {
  color: #ff2a70;
  font-weight: 700;
}

/* Kolom Kanan */
.footer-right {
  display: flex;
  align-items: center;
  gap: 1.25rem;
}

.footer-socials {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.social-icon {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.9);
  border: 1px solid rgba(255, 105, 180, 0.25);
  color: #4b5563;
  text-decoration: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
  transition: all 0.25s ease;
}

.social-icon:hover {
  color: #ffffff;
  background: linear-gradient(135deg, #e60039, #ff2a70);
  border-color: transparent;
  transform: translateY(-2px);
  box-shadow: 0 6px 14px rgba(255, 42, 112, 0.35);
}

/* Tombol Panah Ke Atas */
.btn-back-to-top {
  width: 42px;
  height: 42px;
  border-radius: 12px;
  border: 1.5px solid rgba(255, 105, 180, 0.35);
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.95), rgba(255, 240, 245, 0.9));
  color: #ff2a70;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  outline: none;
  box-shadow: 0 4px 12px rgba(255, 105, 180, 0.15);
  transition: all 0.25s ease;
}

.btn-back-to-top:hover {
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  color: #ffffff;
  border-color: transparent;
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(255, 42, 112, 0.35);
}

.btn-back-to-top:active {
  transform: translateY(0);
}

/* Responsif */
@media (max-width: 768px) {
  .footer {
    padding: 1.5rem 1.25rem;
  }

  .footer-container {
    flex-direction: column;
    text-align: center;
    gap: 1.25rem;
  }

  .footer-right {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
