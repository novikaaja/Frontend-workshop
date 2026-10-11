<script setup>
import { ref } from 'vue'

import proj1 from '../assets/project-1.jpg'
import proj2 from '../assets/project-2.jpg'
import proj3 from '../assets/project-3.jpg'
import proj4 from '../assets/project-4.jpg'
import proj5 from '../assets/project-5.jpg'
import proj6 from '../assets/project-6.jpg'

const scrollContainer = ref(null)

const projects = [
  {
    title: 'Campus Space',
    desc: 'Sistem Peminjaman Tempat',
    tags: ['PHP', 'MySQL', 'Bootstrap'],
    image: proj1,
    link: '#'
  },
  {
    title: 'KpopShop',
    desc: 'UI/UX Design',
    tags: ['Figma'],
    image: proj2,
    link: '#'
  },
  {
    title: 'E-Saving Box',
    desc: 'IoT Project (ESP32)',
    tags: ['Arduino IDE', 'C++', 'Telegram'],
    image: proj3,
    link: '#'
  },
  {
    title: 'Library Silaras',
    desc: 'Sistem Layanan Pustaka Cerdas',
    tags: ['HTML', 'CSS', 'MySQL', 'JavaScript'],
    image: proj4,
    link: '#'
  },
  {
    title: 'Decission Support System',
    desc: 'SPK Pemilihan LMS',
    tags: ['HTML', 'CSS', 'MySQL', 'JavaScript'],
    image: proj5,
    link: '#'
  },
  {
    title: 'Animasi Blender',
    desc: 'Animasi 3D',
    tags: ['Blender'],
    image: proj6,
    link: '#'
  }
]

const scroll = (direction) => {
  if (scrollContainer.value) {
    const scrollAmount = 380
    scrollContainer.value.scrollBy({
      left: direction === 'left' ? -scrollAmount : scrollAmount,
      behavior: 'smooth'
    })
  }
}
</script>

<template>
  <section id="project" class="projects-section">
    <div class="projects-container">
      <!-- Header Section (Center) -->
      <div class="projects-header">
        <div class="section-tag">
          <span class="tag-bar"></span>
          <span class="tag-text">PROJECTS</span>
        </div>
        <h2 class="section-title">Projects</h2>
        <p class="section-subtitle">
          Teknologi dan tools yang saya kuasai untuk mendukung setiap proyek yang saya kerjakan.
        </p>
      </div>

      <!-- Card Slider Bergeser (Horizontal Scroll) -->
      <div ref="scrollContainer" class="projects-slider">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="project-card"
        >
          <!-- Bagian Foto Asli Proyek -->
          <div class="card-image-box">
            <img
              :src="project.image"
              :alt="project.title"
              class="card-img"
              loading="lazy"
            />
            <span class="card-badge">Card {{ index + 1 }}</span>
          </div>

          <!-- Konten Card: Judul, Isi, Komponen Interaktif -->
          <div class="card-content">
            <h3 class="card-title">{{ project.title }}</h3>
            <p class="card-desc">{{ project.desc }}</p>

            <!-- Tag Komponen yang bisa diklik -->
            <div class="card-tags">
              <button
                v-for="tag in project.tags"
                :key="tag"
                type="button"
                class="tag-btn"
                :title="'Filter ' + tag"
              >
                {{ tag }}
              </button>
            </div>

            <!-- Tombol Aksi Detail Proyek -->
            <div class="card-action">
              <a :href="project.link" class="btn-detail">
                <span>Lihat Detail</span>
                <span class="arrow-ico">→</span>
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Navigasi Panah di Tengah Bawah Card -->
      <div class="carousel-controls-bottom">
        <button
          type="button"
          class="nav-arrow prev-arrow"
          aria-label="Previous Project"
          @click="scroll('left')"
        >
          ❮
        </button>
        <button
          type="button"
          class="nav-arrow next-arrow"
          aria-label="Next Project"
          @click="scroll('right')"
        >
          ❯
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-section {
  width: 100%;
  padding: 5rem 2.5rem 6rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.5) 0%, rgba(255, 240, 245, 0.4) 50%, rgba(255, 255, 255, 0.8) 100%);
  position: relative;
  overflow: hidden;
}

.projects-container {
  width: 100%;
  max-width: 1320px;
  margin: 0 auto;
}

/* Header Section (Center) */
.projects-header {
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

/* Slider / Kartu Bergeser */
.projects-slider {
  display: flex;
  gap: 2rem;
  overflow-x: auto;
  padding: 1rem 0.5rem 1.75rem;
  scroll-behavior: smooth;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
}

.projects-slider::-webkit-scrollbar {
  height: 7px;
}

.projects-slider::-webkit-scrollbar-track {
  background: rgba(255, 182, 193, 0.15);
  border-radius: 9999px;
}

.projects-slider::-webkit-scrollbar-thumb {
  background: rgba(255, 105, 180, 0.35);
  border-radius: 9999px;
}

.projects-slider::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 42, 112, 0.65);
}

/* Project Card */
.project-card {
  flex: 0 0 350px;
  scroll-snap-align: start;
  background: rgba(255, 255, 255, 0.9);
  border: 1.5px solid rgba(255, 105, 180, 0.25);
  border-radius: 24px;
  overflow: hidden;
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  box-shadow: 0 8px 24px rgba(255, 105, 180, 0.08);
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  transform: translateY(-6px);
  border-color: #ff2a70;
  box-shadow: 0 16px 36px rgba(255, 42, 112, 0.18);
  background: #ffffff;
}

/* Bagian Foto Asli Proyek */
.card-image-box {
  width: 100%;
  height: 200px;
  position: relative;
  overflow: hidden;
  background: #fdf2f4;
  border-bottom: 1px solid rgba(255, 105, 180, 0.18);
}

.card-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
  display: block;
}

.project-card:hover .card-img {
  transform: scale(1.06);
}

.card-badge {
  position: absolute;
  top: 14px;
  right: 14px;
  padding: 0.3rem 0.8rem;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(8px);
  border-radius: 9999px;
  font-size: 0.75rem;
  font-weight: 700;
  color: #ff2a70;
  border: 1px solid rgba(255, 105, 180, 0.3);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  z-index: 2;
}

/* Konten Card */
.card-content {
  padding: 1.6rem 1.4rem;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.card-title {
  font-size: 1.35rem;
  font-weight: 800;
  color: #111111;
  margin-bottom: 0.45rem;
}

.card-desc {
  font-size: 0.95rem;
  color: #6b7280;
  line-height: 1.5;
  margin-bottom: 1.35rem;
}

/* Tag Komponen yang bisa diklik */
.card-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.55rem;
  margin-bottom: 1.5rem;
}

.tag-btn {
  padding: 0.35rem 0.85rem;
  font-size: 0.78rem;
  font-weight: 600;
  background: rgba(255, 42, 112, 0.08);
  color: #ff2a70;
  border: 1px solid rgba(255, 105, 180, 0.28);
  border-radius: 9999px;
  cursor: pointer;
  outline: none;
  transition: all 0.2s ease;
}

.tag-btn:hover {
  background: linear-gradient(135deg, #e60039, #ff2a70);
  color: #ffffff;
  border-color: transparent;
  transform: translateY(-2px);
  box-shadow: 0 4px 10px rgba(255, 42, 112, 0.28);
}

.tag-btn:active {
  transform: translateY(0);
}

/* Aksi Detail */
.card-action {
  margin-top: auto;
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 105, 180, 0.15);
}

.btn-detail {
  display: inline-flex;
  align-items: center;
  gap: 0.45rem;
  font-size: 0.92rem;
  font-weight: 700;
  color: #ff2a70;
  text-decoration: none;
  transition: all 0.25s ease;
}

.btn-detail:hover {
  color: #e60039;
  transform: translateX(4px);
}

.arrow-ico {
  font-size: 1.1rem;
  transition: transform 0.25s ease;
}

.btn-detail:hover .arrow-ico {
  transform: translateX(3px);
}

/* Navigation Arrows Controls di Tengah Bawah */
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
  .projects-section {
    padding: 3.5rem 1.25rem 4rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .project-card {
    flex: 0 0 300px;
  }
}
</style>
