<script setup lang="ts">
import { ArrowRight } from 'lucide-vue-next';
</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="content">
        <h1 class="headline">
          Igniting Your <span class="highlight">Digital Potential</span>
        </h1>
        <p class="subheadline">
          Premium IT Consulting Services tailored to elevate your business infrastructure using cutting-edge "Agni" (Fire) & "Node" (Tech) methodologies.
        </p>
        <div class="cta-group">
          <a href="#contact" class="btn btn-primary">
            Start Your Journey
            <ArrowRight class="icon" />
          </a>
          <a href="#services" class="btn btn-secondary">
            Explore Services
          </a>
        </div>
      </div>
    </div>
    
    <!-- Background Elements -->
    <div class="bg-glow"></div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 2rem;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  z-index: 10;
  text-align: center;
}

.headline {
  font-size: 3.5rem;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  font-weight: 800;
  letter-spacing: -0.02em;
}

.highlight {
  background: linear-gradient(135deg, var(--color-primary) 0%, #FF8A50 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
}

.subheadline {
  font-size: 1.25rem;
  color: var(--color-text-muted);
  max-width: 700px;
  margin: 0 auto 2.5rem;
  font-weight: 400;
}

.cta-group {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 2rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
  transition: transform 0.2s, box-shadow 0.2s;
}

.btn:hover {
  transform: translateY(-2px);
}

.btn-primary {
  background-color: var(--color-primary);
  color: white;
  box-shadow: 0 4px 14px rgba(255, 87, 34, 0.4);
}

.btn-primary:hover {
  background-color: var(--color-primary-hover);
  box-shadow: 0 6px 20px rgba(255, 87, 34, 0.6);
}

.btn-secondary {
  background-color: rgba(255, 255, 255, 0.05);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
}

.btn-secondary:hover {
  background-color: rgba(255, 255, 255, 0.1);
}

.icon {
  width: 18px;
  height: 18px;
}

/* Background Glow Effect */
.bg-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, rgba(255, 87, 34, 0.15) 0%, rgba(11, 12, 16, 0) 70%);
  z-index: 1;
  pointer-events: none;
}

@media (max-width: 768px) {
  .headline {
    font-size: 2.5rem;
  }
  
  .cta-group {
    flex-direction: column;
  }
  
  .btn {
    width: 100%;
    justify-content: center;
  }
}
</style>
