<script setup>
import { ref } from 'vue'

const scrollContainer = ref(null)

const experiences = [
  {
    role: 'Sekretaris Divisi Komunikasi dan Informasi',
    organization: 'Himpunan Mahasiswa Informatika',
    desc: 'Berkontribusi dalam tim untuk merancang desain UI/UX bertema Environment, Education, dan UMKM.',
    period: '2023 - 2024',
    badgeEmoji: '📢'
  },
  {
    role: 'Ketua Divisi Penalaran dan Kreatifitas',
    organization: 'Himpunan Mahasiswa Informatika',
    desc: 'Mengikuti pelatihan dan workshop pengembangan web dengan fokus pada frontend dan backend.',
    period: '2023 - 2024',
    badgeEmoji: '💡'
  },
  {
    role: 'Staff Divisi Kewirausahaan',
    organization: 'Perhimpunan Mahasiswa Informatika dan Komputer Nasional',
    desc: 'Bertanggung jawab dalam pengelolaan media sosial, dokumentasi, dan publikasi kegiatan organisasi.',
    period: '2023 - 2024',
    badgeEmoji: '💼'
  },
  {
    role: 'Peserta',
    organization: 'Pelatihan Frontend & Backend',
    desc: 'Bertanggung jawab dalam pengelolaan media sosial, dokumentasi, dan publikasi kegiatan organisasi.',
    period: '2023',
    badgeEmoji: '💻'
  },
  {
    role: 'Ketua Divisi',
    organization: 'UI/UX Competition - INFEST UPGRIS',
    desc: 'Berkontribusi dalam tim untuk merancang desain UI/UX bertema Environment, Education, dan UMKM.',
    period: '2023',
    badgeEmoji: '🏆'
  },
  {
    role: 'Peserta',
    organization: 'Pelatihan Web Development',
    desc: 'Mengikuti pelatihan dan workshop pengembangan web dengan fokus pada frontend dan backend.',
    period: '2022',
    badgeEmoji: '🚀'
  }
]

const scroll = (direction) => {
  if (scrollContainer.value) {
    const scrollAmount = 370
    scrollContainer.value.scrollBy({
      left: direction === 'left' ? -scrollAmount : scrollAmount,
      behavior: 'smooth'
    })
  }
}
</script>

<template>
  <section id="experience" class="experience-section">
    <div class="experience-container">
      <!-- Header Section (Center) -->
      <div class="experience-header">
        <div class="section-tag">
          <span class="tag-bar"></span>
          <span class="tag-text">EXPERINCE</span>
        </div>
        <h2 class="section-title">Experince</h2>
        <p class="section-subtitle">
          Pengalaman yang pernah saya alami
        </p>
      </div>

      <!-- Kartu-Kartu Pengalaman Menyamping (Horizontal Slider) -->
      <div ref="scrollContainer" class="experience-slider">
        <div
          v-for="(item, index) in experiences"
          :key="index"
          class="experience-card"
        >
          <!-- Bagian Atas Card -->
          <div class="card-top">
            <div class="icon-circle">
              <span class="emoji-icon">{{ item.badgeEmoji }}</span>
            </div>
            <span class="index-tag">0{{ index + 1 }}</span>
          </div>

          <!-- Judul / Role -->
          <h3 class="role-title">{{ item.role }}</h3>

          <!-- Deskripsi Organisasi / Kegiatan -->
          <div class="org-badge">
            <span class="org-text">{{ item.organization }}</span>
          </div>

          <!-- Isi Uraian Pekerjaan / Kontribusi -->
          <p class="desc-content">
            {{ item.desc }}
          </p>

          <!-- Footer Kartu -->
          <div class="card-footer">
            <span class="period-text">{{ item.period }}</span>
            <span class="dot-indicator"></span>
          </div>
        </div>
      </div>

      <!-- Tombol Navigasi Panah di Tengah Bawah Card -->
      <div class="carousel-controls-bottom">
        <button
          type="button"
          class="nav-arrow prev-arrow"
          aria-label="Previous Experience"
          @click="scroll('left')"
        >
          ❮
        </button>
        <button
          type="button"
          class="nav-arrow next-arrow"
          aria-label="Next Experience"
          @click="scroll('right')"
        >
          ❯
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience-section {
  width: 100%;
  padding: 5rem 2.5rem 6rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.8) 0%, rgba(255, 240, 245, 0.35) 50%, rgba(255, 255, 255, 0.5) 100%);
  position: relative;
  overflow: hidden;
}

.experience-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
}

/* Header Section (Center) */
.experience-header {
  margin-bottom: 2.75rem;
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

/* Slider Menyamping */
.experience-slider {
  display: flex;
  gap: 1.75rem;
  overflow-x: auto;
  padding: 1rem 0.5rem 1.75rem;
  scroll-behavior: smooth;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
}

.experience-slider::-webkit-scrollbar {
  height: 7px;
}

.experience-slider::-webkit-scrollbar-track {
  background: rgba(255, 182, 193, 0.15);
  border-radius: 9999px;
}

.experience-slider::-webkit-scrollbar-thumb {
  background: rgba(255, 105, 180, 0.35);
  border-radius: 9999px;
}

.experience-slider::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 42, 112, 0.65);
}

/* Card Experience Menyamping */
.experience-card {
  flex: 0 0 350px;
  scroll-snap-align: start;
  background: rgba(255, 255, 255, 0.88);
  border: 1.5px solid rgba(255, 105, 180, 0.28);
  border-radius: 24px;
  padding: 1.85rem 1.6rem;
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  box-shadow: 0 8px 24px rgba(255, 105, 180, 0.08);
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  display: flex;
  flex-direction: column;
  position: relative;
}

.experience-card:hover {
  transform: translateY(-6px);
  border-color: #ff2a70;
  box-shadow: 0 16px 36px rgba(255, 42, 112, 0.18);
  background: #ffffff;
}

/* Bagian Atas Card */
.card-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1.25rem;
}

.icon-circle {
  width: 48px;
  height: 48px;
  border-radius: 14px;
  background: rgba(255, 42, 112, 0.08);
  border: 1px solid rgba(255, 105, 180, 0.25);
  display: flex;
  align-items: center;
  justify-content: center;
}

.emoji-icon {
  font-size: 1.4rem;
  line-height: 1;
}

.index-tag {
  font-size: 1.1rem;
  font-weight: 800;
  color: rgba(255, 42, 112, 0.35);
  letter-spacing: 0.05em;
}

/* Judul / Role */
.role-title {
  font-size: 1.25rem;
  font-weight: 800;
  color: #111111;
  line-height: 1.35;
  margin-bottom: 0.75rem;
  min-height: 3.2rem;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* Organisasi / Deskripsi */
.org-badge {
  display: inline-flex;
  align-self: flex-start;
  padding: 0.35rem 0.85rem;
  background: rgba(255, 42, 112, 0.08);
  border: 1px solid rgba(255, 105, 180, 0.25);
  border-radius: 9999px;
  margin-bottom: 1.15rem;
}

.org-text {
  font-size: 0.82rem;
  font-weight: 700;
  color: #ff2a70;
  line-height: 1.3;
}

/* Isi Deskripsi */
.desc-content {
  font-size: 0.95rem;
  color: #4b5563;
  line-height: 1.65;
  margin-bottom: 1.5rem;
  flex: 1;
}

/* Footer Kartu */
.card-footer {
  margin-top: auto;
  padding-top: 1rem;
  border-top: 1px solid rgba(255, 105, 180, 0.16);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.period-text {
  font-size: 0.85rem;
  font-weight: 600;
  color: #9ca3af;
}

.dot-indicator {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background-color: #ff2a70;
  box-shadow: 0 0 8px rgba(255, 42, 112, 0.6);
}

/* Panah Navigasi di Tengah Bawah */
.carousel-controls-bottom {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.25rem;
  margin-top: 2rem;
}

.nav-arrow {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  border: 1.5px solid rgba(255, 105, 180, 0.35);
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(8px);
  color: #ff2a70;
  font-size: 1.25rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.25s ease;
  box-shadow: 0 4px 16px rgba(255, 105, 180, 0.15);
}

.nav-arrow:hover {
  background: linear-gradient(135deg, #e60039, #ff2a70);
  color: #ffffff;
  border-color: transparent;
  transform: translateY(-2px);
  box-shadow: 0 8px 22px rgba(255, 42, 112, 0.35);
}

.nav-arrow:active {
  transform: translateY(0);
}

/* Responsif */
@media (max-width: 640px) {
  .experience-section {
    padding: 3.5rem 1.25rem 4rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .experience-card {
    flex: 0 0 290px;
    padding: 1.4rem 1.25rem;
  }
}
</style>
