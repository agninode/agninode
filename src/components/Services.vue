<script setup lang="ts">
import { Cpu, Cloud, Smartphone, Zap } from 'lucide-vue-next';

const services = [
  {
    icon: Cpu,
    title: 'IT Strategy',
    description: 'Aligning technology with your business goals effectively.'
  },
  {
    icon: Cloud,
    title: 'Cloud Architecture',
    description: 'Scalable and secure cloud solutions for modern enterprises.'
  },
  {
    icon: Smartphone,
    title: 'Digital Transformation',
    description: 'Modernizing legacy systems to meet today’s demands.'
  },
  {
    icon: Zap,
    title: 'Custom Development',
    description: 'Tailored software solutions built for performance.'
  }
];
</script>

<template>
  <section id="services" class="services">
    <div class="container">
      <div class="header">
        <h2 class="section-title">Our Expertise</h2>
        <p class="section-subtitle">Comprehensive solutions for the digital age.</p>
      </div>

      <div class="grid">
        <div v-for="(service, index) in services" :key="index" class="card">
          <div class="icon-wrapper">
            <component :is="service.icon" class="icon" />
          </div>
          <h3 class="card-title">{{ service.title }}</h3>
          <p class="card-desc">{{ service.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
  padding: 6rem 2rem;
  background-color: var(--color-bg);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.section-subtitle {
  color: var(--color-text-muted);
  font-size: 1.1rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.card {
  background-color: var(--color-surface);
  padding: 2.5rem;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.05);
  transition: transform 0.3s, border-color 0.3s;
  cursor: default;
}

.card:hover {
  transform: translateY(-5px);
  border-color: rgba(59, 130, 246, 0.3); /* Secondary Color */
}

.icon-wrapper {
  background-color: rgba(59, 130, 246, 0.1);
  width: 60px;
  height: 60px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  color: var(--color-secondary);
}

.card:hover .icon-wrapper {
  background-color: var(--color-secondary);
  color: white;
}

.icon {
  width: 28px;
  height: 28px;
  transition: color 0.3s;
}

.card-title {
  font-size: 1.25rem;
  margin-bottom: 0.75rem;
}

.card-desc {
  color: var(--color-text-muted);
  font-size: 0.95rem;
  line-height: 1.6;
}
</style>
