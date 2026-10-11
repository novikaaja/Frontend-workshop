<script setup>
const softSkills = [
  { name: 'Komunikasi yang baik', emoji: '💬' },
  { name: 'Mampu bekerja sama tim', emoji: '🤝' },
  { name: 'Disiplin', emoji: '⏰' },
  { name: 'Adaptif', emoji: '🔄' },
  { name: 'Bertanggung jawab', emoji: '⭐' },
]

const hardSkills = [
  { name: 'Desain Canva', emoji: '🎨' },
  { name: 'Desain Figma', emoji: '📐' },
  { name: 'Microsoft Office (Word, Excel, PowerPoint)', emoji: '📊' },
]
</script>

<template>
  <section id="skills" class="skills-section">
    <div class="skills-container">
      <!-- Header Section Skills (Center) -->
      <div class="skills-header">
        <div class="section-tag">
          <span class="tag-bar"></span>
          <span class="tag-text">SKILLS</span>
        </div>
        <h2 class="section-title">Skills</h2>
        <p class="section-subtitle">
          Teknologi dan tools yang saya kuasai untuk mendukung setiap proyek yang saya kerjakan.
        </p>
      </div>

      <!-- 2 Kolom Skills -->
      <div class="skills-content">
        <!-- Kolom Kiri: Soft Skills -->
        <div class="skills-column">
          <div class="category-header">
            <button type="button" class="btn-category">
              Soft Skills
            </button>
          </div>

          <div class="skills-list">
            <div
              v-for="(skill, index) in softSkills"
              :key="index"
              class="skill-item"
            >
              <span class="skill-emoji">{{ skill.emoji }}</span>
              <span class="skill-name">{{ skill.name }}</span>
            </div>
          </div>
        </div>

        <!-- Kolom Kanan: Hard Skills -->
        <div class="skills-column">
          <div class="category-header">
            <button type="button" class="btn-category">
              Hard Skills
            </button>
          </div>

          <div class="skills-list">
            <div
              v-for="(skill, index) in hardSkills"
              :key="index"
              class="skill-item"
            >
              <span class="skill-emoji">{{ skill.emoji }}</span>
              <span class="skill-name">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills-section {
  width: 100%;
  padding: 5rem 2.5rem 6rem;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0.4) 0%, rgba(255, 240, 245, 0.35) 50%, rgba(255, 255, 255, 0.6) 100%);
  position: relative;
}

.skills-container {
  width: 100%;
  max-width: 1240px;
  margin: 0 auto;
}

/* Header Section (Center) */
.skills-header {
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
.skills-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3.5rem;
}

.skills-column {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.category-header {
  display: flex;
}

/* Button Kategori (Warna pink, tulisan putih, stroke pink) */
.btn-category {
  padding: 0.75rem 2rem;
  font-size: 1.05rem;
  font-weight: 700;
  color: #ffffff;
  background: linear-gradient(135deg, #e60039 0%, #ff2a70 50%, #ff6fa0 100%);
  border: 2px solid #ff2a70;
  border-radius: 9999px;
  cursor: default;
  box-shadow: 0 4px 16px rgba(255, 42, 112, 0.28);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.btn-category:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(255, 42, 112, 0.38);
}

/* List Button / Item Ke Bawah */
.skills-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.skill-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.05rem 1.4rem;
  background: rgba(255, 255, 255, 0.85);
  border: 1.5px solid rgba(255, 105, 180, 0.3);
  border-radius: 16px;
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  box-shadow: 0 4px 14px rgba(255, 105, 180, 0.06);
  transition: all 0.3s ease;
  cursor: default;
}

.skill-item:hover {
  transform: translateX(6px);
  background: #ffffff;
  border-color: #ff2a70;
  box-shadow: 0 6px 20px rgba(255, 42, 112, 0.16);
}

.skill-emoji {
  font-size: 1.35rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 42px;
  height: 42px;
  background: rgba(255, 42, 112, 0.08);
  border-radius: 12px;
  flex-shrink: 0;
}

.skill-name {
  font-size: 1rem;
  font-weight: 600;
  color: #1f2937;
  line-height: 1.4;
}

/* Responsive */
@media (max-width: 868px) {
  .skills-content {
    grid-template-columns: 1fr;
    gap: 2.75rem;
  }
}

@media (max-width: 640px) {
  .skills-section {
    padding: 3.5rem 1.25rem 4rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .btn-category {
    width: 100%;
    text-align: center;
  }
}
</style>
