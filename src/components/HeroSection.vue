<script setup>
import novikaImg from '../assets/novika.jpeg'

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
    href: 'mailto:novika@example.com',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>`
  }
]
</script>

<template>
  <section id="home" class="hero-section">
    <div class="hero-container">
      <!-- Kolom Kiri -->
      <div class="hero-left">
        <div class="hero-titles">
          <h1 class="title-dark">Portofolio</h1>
          <h2 class="title-pink">Luriyanti Novika</h2>
          <h3 class="title-dark">Purnama Sari</h3>
        </div>

        <p class="hero-desc">
          Saya adalah mahasiswa Informatika yang tertarik pada
          pengembangan web, desain antarmuka, dan teknologi untuk
          menciptakan solusi digital yang bermanfaat.
        </p>

        <!-- 2 Button Bersebelahan -->
        <div class="hero-buttons">
          <a href="#project" class="btn-primary">Lihat Proyek Saya</a>
          <a href="#about" class="btn-secondary">Tentang Saya</a>
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

      <!-- Kolom Kanan -->
      <div class="hero-right">
        <!-- Banner Miring: Let's Build Something Great! -->
        <div class="slanted-text">
          <span>Let's Build Something Great!</span>
        </div>

        <div class="photo-wrapper">
          <!-- Background Bentuk Random Transparan Pink -->
          <div class="blob-bg blob-1"></div>
          <div class="blob-bg blob-2"></div>

          <!-- Foto Profil Ukuran 455 x 570 -->
          <div class="image-box">
            <img
              :src="novikaImg"
              alt="Luriyanti Novika Purnama Sari"
              class="profile-img"
            />
          </div>

          <!-- Button Transparan Kecil dengan emotion love pink -->
          <div class="floating-badge">
            <span class="badge-love">💖</span>
            <span class="badge-text">Always learning always growing</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  width: 100%;
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  padding: 7rem 2.5rem 5rem;
  overflow: hidden;
  background: radial-gradient(circle at 85% 30%, rgba(255, 182, 193, 0.35) 0%, rgba(255, 255, 255, 0.2) 65%, transparent 100%),
              radial-gradient(circle at 10% 70%, rgba(255, 192, 203, 0.2) 0%, transparent 60%);
}

.hero-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1.15fr 0.95fr;
  align-items: center;
  gap: 3.5rem;
}

/* Kolom Kiri */
.hero-left {
  display: flex;
  flex-direction: column;
  z-index: 2;
}

.hero-titles {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
  margin-bottom: 1.5rem;
}

.title-dark {
  font-size: 3.25rem;
  font-weight: 800;
  color: #111111;
  line-height: 1.12;
  letter-spacing: -0.03em;
}

.title-pink {
  font-size: 3.45rem;
  font-weight: 900;
  line-height: 1.12;
  letter-spacing: -0.03em;
  background: linear-gradient(135deg, #e60067 0%, #ff2a70 50%, #ff69b4 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 4px 16px rgba(255, 42, 112, 0.2));
}

.hero-desc {
  font-size: 1.125rem;
  line-height: 1.75;
  color: #4a5568;
  max-width: 580px;
  margin-bottom: 2.25rem;
}

/* Button Bersebelahan */
.hero-buttons {
  display: flex;
  align-items: center;
  gap: 1.25rem;
  margin-bottom: 2.75rem;
}

.btn-primary {
  padding: 0.85rem 1.85rem;
  border-radius: 9999px;
  font-size: 1rem;
  font-weight: 600;
  color: #ffffff;
  text-decoration: none;
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  box-shadow: 0 6px 18px rgba(230, 0, 57, 0.35);
  transition: all 0.25s ease;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(230, 0, 57, 0.45);
}

.btn-secondary {
  padding: 0.82rem 1.85rem;
  border-radius: 9999px;
  font-size: 1rem;
  font-weight: 600;
  color: #111111;
  text-decoration: none;
  background: rgba(255, 255, 255, 0.85);
  border: 1.5px solid rgba(255, 42, 112, 0.35);
  backdrop-filter: blur(8px);
  transition: all 0.25s ease;
}

.btn-secondary:hover {
  border-color: #ff2a70;
  color: #ff2a70;
  transform: translateY(-2px);
  background: rgba(255, 240, 245, 0.9);
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
  background: rgba(255, 255, 255, 0.8);
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

/* Kolom Kanan */
.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

/* Tulisan Miring Di Samping Foto */
.slanted-text {
  position: absolute;
  top: 18%;
  left: -48px;
  z-index: 5;
  transform: rotate(-14deg);
  background: rgba(255, 255, 255, 0.9);
  padding: 0.6rem 1.4rem;
  border-radius: 14px;
  border: 1.5px solid rgba(255, 105, 180, 0.35);
  box-shadow: 0 10px 24px rgba(255, 105, 180, 0.2);
  backdrop-filter: blur(10px);
  pointer-events: none;
  animation: floatSlow 4s ease-in-out infinite alternate;
}

.slanted-text span {
  font-size: 1.05rem;
  font-weight: 800;
  letter-spacing: -0.01em;
  background: linear-gradient(135deg, #ff1493, #e60039);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  white-space: nowrap;
}

/* Photo Wrapper & Blobs */
.photo-wrapper {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Latar belakang bentuk random transparan pink */
.blob-bg {
  position: absolute;
  z-index: 1;
  filter: blur(10px);
  pointer-events: none;
}

.blob-1 {
  width: 530px;
  height: 640px;
  background: rgba(255, 182, 193, 0.42);
  border-radius: 42% 58% 70% 30% / 45% 45% 55% 55%;
  animation: blobMorph 10s ease-in-out infinite alternate;
}

.blob-2 {
  width: 480px;
  height: 590px;
  background: rgba(255, 105, 180, 0.25);
  border-radius: 58% 42% 38% 62% / 54% 60% 40% 46%;
  animation: blobMorph 12s ease-in-out infinite alternate-reverse;
}

/* Kotak Foto */
.image-box {
  width: 355px;
  height: 470px;
  max-width: 100%;
  border-radius: 32px;
  overflow: hidden;
  position: relative;
  z-index: 2;
  box-shadow: 0 12px 30px -6px rgba(255, 105, 180, 0.12),
              0 4px 12px -2px rgba(0, 0, 0, 0.05);
  border: 4px solid rgba(255, 255, 255, 0.85);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.image-box:hover {
  transform: scale(1.02);
  box-shadow: 0 16px 36px -6px rgba(255, 105, 180, 0.18),
              0 6px 16px -2px rgba(0, 0, 0, 0.06);
}

.profile-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Button Transparan Kecil "Always learning always growing" */
.floating-badge {
  position: absolute;
  bottom: 24px;
  right: -20px;
  z-index: 4;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.65rem 1.15rem;
  background: rgba(255, 255, 255, 0.68);
  border: 1px solid rgba(255, 105, 180, 0.35);
  border-radius: 9999px;
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  box-shadow: 0 8px 24px rgba(230, 0, 57, 0.15);
  cursor: default;
  transition: transform 0.25s ease, background 0.25s ease;
  user-select: none;
}

.floating-badge:hover {
  transform: translateY(-3px);
  background: rgba(255, 255, 255, 0.85);
}

.badge-love {
  font-size: 1.1rem;
  line-height: 1;
}

.badge-text {
  font-size: 0.88rem;
  font-weight: 600;
  color: #333333;
  white-space: nowrap;
}

/* Keyframes */
@keyframes blobMorph {
  0% {
    border-radius: 42% 58% 70% 30% / 45% 45% 55% 55%;
    transform: rotate(0deg);
  }
  50% {
    border-radius: 50% 50% 33% 67% / 55% 27% 73% 45%;
    transform: rotate(5deg) scale(1.03);
  }
  100% {
    border-radius: 65% 35% 45% 55% / 35% 65% 35% 65%;
    transform: rotate(-3deg);
  }
}

@keyframes floatSlow {
  0% {
    transform: rotate(-14deg) translateY(0px);
  }
  100% {
    transform: rotate(-12deg) translateY(-8px);
  }
}

/* Responsif */
@media (max-width: 1100px) {
  .hero-container {
    grid-template-columns: 1fr;
    gap: 4rem;
    text-align: center;
  }

  .hero-left {
    align-items: center;
  }

  .hero-desc {
    margin-left: auto;
    margin-right: auto;
  }

  .hero-buttons {
    justify-content: center;
  }

  .social-medias {
    justify-content: center;
  }

  .slanted-text {
    left: 0;
    top: 10px;
  }
}

@media (max-width: 540px) {
  .hero-section {
    padding: 6rem 1.25rem 4rem;
  }

  .title-dark {
    font-size: 2.2rem;
  }

  .title-pink {
    font-size: 2.4rem;
  }

  .image-box {
    width: 320px;
    height: 400px;
  }

  .blob-1, .blob-2 {
    width: 340px;
    height: 420px;
  }

  .hero-buttons {
    flex-direction: column;
    width: 100%;
  }

  .btn-primary, .btn-secondary {
    width: 100%;
    text-align: center;
  }

  .floating-badge {
    right: 0;
    bottom: -15px;
    padding: 0.5rem 0.9rem;
  }
  
  .badge-text {
    font-size: 0.78rem;
  }
}
</style>
