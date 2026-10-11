<script setup>
import novikaImg from '../assets/novika.jpeg'

const infoCards = [
  {
    title: 'Lokasi',
    desc: 'Blora, Jawa Tengah',
    icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ff2a70" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>`
  },
  {
    title: 'Email',
    desc: 'nopiajalahya@gmail.com',
    icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ff2a70" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="16" x="2" y="4" rx="2"></rect><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"></path></svg>`
  },
  {
    title: 'Pendidikan',
    desc: 'Universitas PGRI Semarang',
    icon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ff2a70" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"></path><path d="M6 12v5c3 3 9 3 12 0v-5"></path></svg>`
  }
]
</script>

<template>
  <section id="about" class="about-section">
    <div class="about-container">
      <!-- Header Section About -->
      <div class="about-header">
        <div class="section-tag">
          <span class="tag-bar"></span>
          <span class="tag-text">TENTANG SAYA</span>
        </div>
        <h2 class="section-title">About Me</h2>
        <p class="section-subtitle">
          Teknologi dan tools yang saya kuasai untuk mendukung setiap proyek yang saya kerjakan.
        </p>
      </div>

      <!-- 2 Kolom Konten -->
      <div class="about-content">
        <!-- Kolom Kiri -->
        <div class="about-left">
          <p class="about-description">
            Halo! Saya <span class="highlight-pink">Luriyanti Novika Purnama Sari</span>, seorang mahasiswa Informatika yang memiliki ketertarikan di bidang pengembangan web, desain UI/UX, dan teknologi digital. Saya senang belajar hal baru, bekerja dalam tim, dan selalu berusaha memberikan hasil terbaik dalam setiap proyek.
          </p>

          <!-- 3 Button / Card Kebawah -->
          <div class="info-list">
            <div
              v-for="(item, idx) in infoCards"
              :key="idx"
              class="info-card"
            >
              <div class="icon-wrapper" v-html="item.icon"></div>
              <div class="info-text">
                <span class="info-title">{{ item.title }}</span>
                <span class="info-desc">{{ item.desc }}</span>
              </div>
            </div>
          </div>

          <!-- Button Lebih Besar: Lebih lanjut ➔ -->
          <div class="cta-wrapper">
            <a href="#more" class="btn-more">
              <span>Lebih lanjut</span>
              <span class="arrow-icon">➔</span>
            </a>
          </div>
        </div>

        <!-- Kolom Kanan -->
        <div class="about-right">
          <div class="photo-container">
            <img
              :src="novikaImg"
              alt="Luriyanti Novika Purnama Sari"
              class="about-img"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  width: 100%;
  padding: 5rem 2.5rem 6rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0) 0%, rgba(255, 240, 245, 0.45) 50%, rgba(255, 255, 255, 0) 100%);
  position: relative;
}

.about-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
}

/* Header Section */
.about-header {
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

/* 2 Kolom Konten */
.about-content {
  display: grid;
  grid-template-columns: 1.15fr 0.95fr;
  align-items: center;
  gap: 4rem;
}

/* Kolom Kiri */
.about-left {
  display: flex;
  flex-direction: column;
}

.about-description {
  font-size: 1.1rem;
  line-height: 1.85;
  color: #6b7280;
  margin-bottom: 2.25rem;
}

.highlight-pink {
  color: #ff2a70;
  font-weight: 700;
}

/* 3 Tombol / Kartu Informasi */
.info-list {
  display: flex;
  flex-direction: column;
  gap: 1.1rem;
  margin-bottom: 2.25rem;
}

.info-card {
  display: flex;
  align-items: center;
  gap: 1.25rem;
  padding: 1rem 1.4rem;
  background: rgba(255, 255, 255, 0.75);
  border: 1.5px solid rgba(255, 105, 180, 0.35);
  border-radius: 16px;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(255, 105, 180, 0.05);
  cursor: default;
}

.info-card:hover {
  transform: translateX(6px);
  background: rgba(255, 255, 255, 0.95);
  border-color: #ff2a70;
  box-shadow: 0 6px 20px rgba(255, 42, 112, 0.15);
}

.icon-wrapper {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: rgba(255, 42, 112, 0.08);
  border: 1px solid rgba(255, 42, 112, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.info-text {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
}

.info-title {
  font-size: 0.88rem;
  font-weight: 700;
  color: #ff2a70;
  text-transform: capitalize;
}

.info-desc {
  font-size: 1rem;
  font-weight: 600;
  color: #1f2937;
}

/* Button Lebih Besar */
.cta-wrapper {
  margin-top: 0.5rem;
}

.btn-more {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.95rem 2.2rem;
  font-size: 1.05rem;
  font-weight: 700;
  color: #ff2a70;
  background-color: #ffffff;
  border: 2px solid #ff2a70;
  border-radius: 9999px;
  text-decoration: none;
  box-shadow: 0 6px 20px rgba(255, 42, 112, 0.18);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.btn-more:hover {
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  color: #ffffff;
  transform: translateY(-2px);
  box-shadow: 0 10px 28px rgba(255, 42, 112, 0.38);
}

.arrow-icon {
  font-size: 1.15rem;
  transition: transform 0.25s ease;
}

.btn-more:hover .arrow-icon {
  transform: translateX(4px);
}

/* Kolom Kanan (Foto) */
.about-right {
  display: flex;
  justify-content: center;
  align-items: center;
}

.photo-container {
  width: 355px;
  height: 470px;
  max-width: 100%;
  border-radius: 28px;
  overflow: hidden;
  position: relative;
  border: 3px solid rgba(255, 105, 180, 0.85);
  box-shadow: 0 18px 45px rgba(255, 105, 180, 0.32),
              0 6px 18px rgba(230, 0, 57, 0.18);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
}

.photo-container:hover {
  transform: translateY(-5px);
  box-shadow: 0 24px 55px rgba(255, 42, 112, 0.42),
              0 8px 24px rgba(230, 0, 57, 0.25);
}

.about-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Responsif */
@media (max-width: 1024px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3.5rem;
  }

  .about-left {
    order: 2;
  }

  .about-right {
    order: 1;
  }

  .section-subtitle {
    max-width: 100%;
  }
}

@media (max-width: 640px) {
  .about-section {
    padding: 3.5rem 1.25rem 4rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .photo-container {
    width: 290px;
    height: 384px;
  }

  .btn-more {
    width: 100%;
    justify-content: center;
  }
}
</style>
