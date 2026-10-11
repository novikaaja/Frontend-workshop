<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ProjectSection from './components/ProjectSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div class="app-layout">
    <!-- Header Fixed -->
    <Header />

    <!-- Main Content -->
    <main>
      <!-- Hero Section -->
      <HeroSection />

      <!-- About Section -->
      <AboutSection />

      <!-- Skills Section -->
      <SkillsSection />

      <!-- Project Section -->
      <ProjectSection />

      <!-- Experience Section -->
      <ExperienceSection />

      <!-- Contact Section -->
      <ContactSection />
    </main>

    <!-- Footer -->
    <FooterSection />
  </div>
</template>

<style scoped>
.app-layout {
  width: 100%;
  min-height: 100vh;
}
</style>
