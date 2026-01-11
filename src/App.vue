<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { Network } from 'lucide-vue-next';
import Hero from './components/Hero.vue';
import Services from './components/Services.vue';
import About from './components/About.vue';
import Contact from './components/Contact.vue';

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;
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
    <header class="navbar-wrapper">
      <div class="navbar" :class="{ 'scrolled': isScrolled }">
        <a href="#" class="logo">
          <div class="icon-bg">
            <Network class="logo-icon" />
          </div>
          <span>Agninode</span>
        </a>

        <nav class="nav-links">
          <a href="#services">サービス</a>
          <a href="#about">私たちについて</a>
          <a href="#contact" class="nav-cta">お問い合わせ</a>
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

.navbar-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 1rem 1rem;
  z-index: 100;
  pointer-events: none;
  /* Let clicks pass through wrapper */
}

.navbar {
  max-width: 1000px;
  margin: 0 auto;
  padding: 0.8rem 1.5rem;
  background-color: rgba(20, 21, 28, 0.8);
  backdrop-filter: blur(16px);
  border-radius: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  pointer-events: auto;
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.navbar.scrolled {
  background-color: rgba(11, 12, 16, 0.95);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
  transform: translateY(5px);
  border-color: var(--color-primary);
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-weight: 800;
  font-size: 1.4rem;
  color: var(--color-text-main);
}

.icon-bg {
  width: 36px;
  height: 36px;
  background-color: var(--color-primary);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}

.logo-icon {
  width: 20px;
  height: 20px;
}

.nav-links {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-links a:not(.nav-cta) {
  font-weight: 700;
  font-size: 0.95rem;
  color: var(--color-text-muted);
  transition: color 0.2s;
}

.nav-links a:not(.nav-cta):hover {
  color: white;
}

.nav-cta {
  background-color: white;
  color: var(--color-bg);
  padding: 0.6rem 1.5rem;
  border-radius: 50px;
  font-weight: 700;
  font-size: 0.9rem;
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.nav-cta:hover {
  background-color: var(--color-primary);
  transform: scale(1.05);
  box-shadow: 0 4px 12px rgba(255, 107, 107, 0.4);
}

@media (max-width: 768px) {
  .nav-links a:not(.nav-cta) {
    display: none;
  }
}
</style>
