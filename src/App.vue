<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { Network } from 'lucide-vue-next';
import Hero from './components/Hero.vue';
import Services from './components/Services.vue';
import About from './components/About.vue';
import Contact from './components/Contact.vue';

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="app-layout">
    <header class="navbar" :class="{ 'scrolled': isScrolled }">
      <div class="nav-container">
        <a href="#" class="logo">
          <Network class="logo-icon" />
          <span>Agninode</span>
        </a>
        
        <nav class="nav-links">
          <a href="#services">Services</a>
          <a href="#about">About</a>
          <a href="#contact" class="nav-cta">Contact</a>
        </nav>
      </div>
    </header>

    <main>
      <Hero />
      <Services />
      <About />
      <Contact />
    </main>
  </div>
</template>

<style scoped>
.app-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 1.5rem 2rem;
  z-index: 100;
  transition: all 0.3s ease;
}

.navbar.scrolled {
  padding: 1rem 2rem;
  background-color: rgba(11, 12, 16, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 700;
  font-size: 1.5rem;
  font-family: var(--font-heading);
}

.logo-icon {
  width: 28px;
  height: 28px;
  color: var(--color-primary);
}

.nav-links {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-links a:not(.nav-cta) {
  font-weight: 500;
  position: relative;
}

.nav-links a:not(.nav-cta):hover {
  color: white;
}

.nav-links a:not(.nav-cta)::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-primary);
  transition: width 0.2s;
}

.nav-links a:not(.nav-cta):hover::after {
  width: 100%;
}

.nav-cta {
  background-color: white;
  color: var(--color-bg);
  padding: 0.5rem 1.25rem;
  border-radius: 50px;
  font-weight: 600;
  transition: background-color 0.2s, transform 0.2s;
}

.nav-cta:hover {
  background-color: #f0f0f0;
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .nav-links a:not(.nav-cta) {
    display: none; /* Hide links on mobile for simplicity, keep CTA if possible or clean up */
  }
}
</style>
