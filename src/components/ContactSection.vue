<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const isSubmitted = ref(false)

const socialLinks = [
  {
    name: 'Github',
    href: 'https://github.com',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.53 1.032 1.53 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>`
  },
  {
    name: 'WhatsApp',
    href: 'https://whatsapp.com',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.301-.15-1.78-.878-2.056-.979-.275-.101-.475-.15-.675.15-.2.3-.775.979-.95 1.179-.175.2-.351.226-.651.075s-1.27-.468-2.42-1.493c-.895-.798-1.5-1.784-1.675-2.084s-.019-.462.131-.611c.135-.134.301-.35.451-.525.15-.175.2-.3.3-.5.1-.2.05-.376-.025-.526s-.675-1.628-.925-2.23c-.244-.585-.492-.506-.675-.515-.175-.009-.375-.01-.575-.01s-.525.075-.8.375c-.275.3-1.05 1.027-1.05 2.505s1.075 2.905 1.225 3.105c.15.2 2.115 3.23 5.124 4.53 3.01 1.3 3.01.868 3.56.818.55-.05 1.78-.727 2.03-1.429.25-.702.25-1.303.175-1.429-.075-.125-.275-.2-.576-.35zM12.04 2C6.54 2 2.08 6.46 2.08 11.96c0 1.97.58 3.81 1.58 5.37L2 22l4.82-1.59a9.92 9.92 0 005.22 1.47h.005c5.5 0 9.96-4.46 9.96-9.96A9.97 9.97 0 0012.04 2z"/></svg>`
  },
  {
    name: 'Instagram',
    href: 'https://instagram.com',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>`
  },
  {
    name: 'Email',
    href: 'mailto:nopiajalahya@gmail.com',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>`
  }
]

const handleSubmit = () => {
  isSubmitted.value = true
  setTimeout(() => {
    alert('Pesan berhasil dikirim! Terima kasih.')
    form.value = { name: '', email: '', subject: '', message: '' }
    isSubmitted.value = false
  }, 500)
}
</script>

<template>
  <section id="contact" class="contact-section">
    <div class="contact-container">
      <!-- Header Section (Center) -->
      <div class="contact-header">
        <div class="section-tag">
          <span class="tag-bar"></span>
          <span class="tag-text">HUBUNGI KAMI</span>
        </div>
        <h2 class="section-title">Get In Touch</h2>
        <p class="section-subtitle">
          hubungi saya jika perlu
        </p>
      </div>

      <!-- 2 Kolom Contact -->
      <div class="contact-content">
        <!-- Kolom Kiri -->
        <div class="contact-left">
          <p class="contact-desc">
            Jika kamu tertarik untuk bekerja sama, punya pertanyaan,
            atau sekadar ingin berbincang, jangan ragu untuk
            menghubungi saya!
          </p>

          <!-- Button dengan Logo Email & Lokasi -->
          <div class="info-buttons">
            <a href="mailto:nopiajalahya@gmail.com" class="contact-btn">
              <div class="btn-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ff2a70" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <rect width="20" height="16" x="2" y="4" rx="2"></rect>
                  <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path>
                </svg>
              </div>
              <div class="btn-info">
                <span class="info-label">Email</span>
                <span class="info-val">nopiajalahya@gmail.com</span>
              </div>
            </a>

            <div class="contact-btn">
              <div class="btn-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ff2a70" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                  <circle cx="12" cy="10" r="3"></circle>
                </svg>
              </div>
              <div class="btn-info">
                <span class="info-label">Lokasi</span>
                <span class="info-val">Blora, Jawa Tengah</span>
              </div>
            </div>
          </div>

          <!-- 4 Logo Sosial Media -->
          <div class="social-medias">
            <a
              v-for="item in socialLinks"
              :key="item.name"
              :href="item.href"
              :title="item.name"
              target="_blank"
              rel="noopener noreferrer"
              class="social-btn"
              v-html="item.icon"
            ></a>
          </div>
        </div>

        <!-- Kolom Kanan (Form Kirim Pesan) -->
        <div class="contact-right">
          <form class="contact-form" @submit.prevent="handleSubmit">
            <div class="form-group">
              <label for="name" class="form-label">Nama Lengkap</label>
              <input
                id="name"
                v-model="form.name"
                type="text"
                class="form-input"
                placeholder="Masukkan nama Anda..."
                required
              />
            </div>

            <div class="form-group">
              <label for="email" class="form-label">Alamat Email</label>
              <input
                id="email"
                v-model="form.email"
                type="email"
                class="form-input"
                placeholder="Masukkan email Anda..."
                required
              />
            </div>

            <div class="form-group">
              <label for="subject" class="form-label">Subjek</label>
              <input
                id="subject"
                v-model="form.subject"
                type="text"
                class="form-input"
                placeholder="Topik pesan..."
                required
              />
            </div>

            <div class="form-group">
              <label for="message" class="form-label">Pesan</label>
              <textarea
                id="message"
                v-model="form.message"
                rows="4"
                class="form-textarea"
                placeholder="Tulis pesan Anda di sini..."
                required
              ></textarea>
            </div>

            <button type="submit" class="btn-submit">
              <span>Kirim Pesan</span>
              <span class="send-icon">🚀</span>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  width: 100%;
  padding: 5rem 2.5rem 6.5rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.4) 0%, rgba(255, 240, 245, 0.45) 50%, rgba(255, 255, 255, 0.9) 100%);
  position: relative;
}

.contact-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
}

/* Header Section (Center) */
.contact-header {
  margin-bottom: 3.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 0.5rem;
}

.section-tag {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.55rem;
}

.tag-bar {
  display: inline-block;
  width: 5px;
  height: 18px;
  background-color: #ff2a70;
  border-radius: 4px;
}

.tag-text {
  font-size: 0.92rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  color: #ff2a70;
  text-transform: uppercase;
}

.section-title {
  font-size: 2.75rem;
  font-weight: 800;
  color: #111111;
  letter-spacing: -0.02em;
  line-height: 1.2;
}

.section-subtitle {
  font-size: 1.05rem;
  color: #6b7280;
  max-width: 680px;
  margin: 0 auto;
  line-height: 1.6;
}

/* 2 Kolom Layout */
.contact-content {
  display: grid;
  grid-template-columns: 1.05fr 1.15fr;
  align-items: start;
  gap: 4.5rem;
}

/* Kolom Kiri */
.contact-left {
  display: flex;
  flex-direction: column;
}

.contact-desc {
  font-size: 1.15rem;
  line-height: 1.85;
  color: #6b7280;
  margin-bottom: 2.25rem;
}

/* Button Email & Lokasi */
.info-buttons {
  display: flex;
  flex-direction: column;
  gap: 1.15rem;
  margin-bottom: 2.5rem;
}

.contact-btn {
  display: flex;
  align-items: center;
  gap: 1.25rem;
  padding: 1.05rem 1.4rem;
  background: rgba(255, 255, 255, 0.85);
  border: 1.5px solid rgba(255, 105, 180, 0.3);
  border-radius: 18px;
  text-decoration: none;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  box-shadow: 0 4px 16px rgba(255, 105, 180, 0.06);
  transition: all 0.3s ease;
  color: inherit;
}

.contact-btn:hover {
  transform: translateX(6px);
  background: #ffffff;
  border-color: #ff2a70;
  box-shadow: 0 8px 24px rgba(255, 42, 112, 0.15);
}

.btn-icon {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  background: rgba(255, 42, 112, 0.08);
  border: 1px solid rgba(255, 105, 180, 0.25);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.btn-info {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
}

.info-label {
  font-size: 0.85rem;
  font-weight: 700;
  color: #ff2a70;
  text-transform: capitalize;
}

.info-val {
  font-size: 1.05rem;
  font-weight: 600;
  color: #1f2937;
}

/* 4 Logo Media Sosial */
.social-medias {
  display: flex;
  align-items: center;
  gap: 1.1rem;
}

.social-btn {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.85);
  border: 1px solid rgba(255, 105, 180, 0.25);
  color: #333333;
  text-decoration: none;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
  backdrop-filter: blur(6px);
  transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
}

.social-btn:hover {
  color: #ffffff;
  background: linear-gradient(135deg, #e60039, #ff2a70);
  border-color: transparent;
  transform: translateY(-3px);
  box-shadow: 0 8px 18px rgba(255, 42, 112, 0.35);
}

/* Kolom Kanan (Form) */
.contact-right {
  display: flex;
}

.contact-form {
  width: 100%;
  background: rgba(255, 255, 255, 0.9);
  border: 1.5px solid rgba(255, 105, 180, 0.28);
  border-radius: 28px;
  padding: 2.5rem 2.25rem;
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  box-shadow: 0 12px 35px rgba(255, 105, 180, 0.1);
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.45rem;
}

.form-label {
  font-size: 0.9rem;
  font-weight: 700;
  color: #374151;
}

.form-input,
.form-textarea {
  width: 100%;
  padding: 0.85rem 1.15rem;
  font-size: 0.95rem;
  font-family: inherit;
  color: #1f2937;
  background: rgba(255, 245, 247, 0.6);
  border: 1.5px solid rgba(255, 182, 193, 0.4);
  border-radius: 14px;
  outline: none;
  transition: all 0.25s ease;
}

.form-textarea {
  resize: vertical;
  min-height: 110px;
}

.form-input:focus,
.form-textarea:focus {
  background: #ffffff;
  border-color: #ff2a70;
  box-shadow: 0 0 0 3px rgba(255, 42, 112, 0.12);
}

.btn-submit {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
  padding: 0.95rem 2rem;
  margin-top: 0.5rem;
  border: none;
  border-radius: 9999px;
  font-size: 1rem;
  font-weight: 700;
  color: #ffffff;
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  box-shadow: 0 6px 20px rgba(230, 0, 57, 0.35);
  cursor: pointer;
  outline: none;
  transition: all 0.25s ease;
}

.btn-submit:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(230, 0, 57, 0.45);
}

.btn-submit:active {
  transform: translateY(0);
}

.send-icon {
  font-size: 1.1rem;
  transition: transform 0.25s ease;
}

.btn-submit:hover .send-icon {
  transform: translateX(4px) translateY(-2px);
}

/* Responsif */
@media (max-width: 960px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 3.5rem;
  }
}

@media (max-width: 640px) {
  .contact-section {
    padding: 3.5rem 1.25rem 4rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .contact-form {
    padding: 1.75rem 1.4rem;
  }
}
</style>
