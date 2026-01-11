<script setup lang="ts">
import { Flame, Share2 } from 'lucide-vue-next';
</script>

<template>
  <section id="about" class="about">
    <div class="container">
      <div class="content">
        <div class="text-col">
          <h2 class="section-title">Why <span class="highlight">Agninode</span>?</h2>
          <p class="description">
            The name <strong>"Agninode"</strong> represents the fusion of two powerful forces:
          </p>
          
          <div class="feature-list">
            <div class="feature-item">
              <div class="icon-box primary-box">
                <Flame class="icon" />
              </div>
              <div>
                <h3>Agni (Fire)</h3>
                <p>Represents passion, energy, and the transformative power of innovation.</p>
              </div>
            </div>
            
            <div class="feature-item">
              <div class="icon-box secondary-box">
                <Share2 class="icon" />
              </div>
              <div>
                <h3>Node (Connection)</h3>
                <p>Symbolizes technology, networking, and the critical points of your digital infrastructure.</p>
              </div>
            </div>
          </div>
          
          <p class="mission">
            Our mission is to ignite your business potential through robust, scalable technological solutions.
          </p>
        </div>
        
        <div class="visual-col">
          <div class="circle-graphic">
            <div class="circle c1"></div>
            <div class="circle c2"></div>
            <div class="circle c3"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 8rem 2rem;
  background-color: var(--color-bg);
  position: relative;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

.highlight {
  color: var(--color-primary);
}

.description {
  color: var(--color-text-muted);
  font-size: 1.1rem;
  margin-bottom: 3rem;
}

.feature-list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-bottom: 3rem;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 1.5rem;
}

.icon-box {
  width: 50px;
  height: 50px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.primary-box {
  background-color: rgba(255, 87, 34, 0.1);
  color: var(--color-primary);
}

.secondary-box {
  background-color: rgba(59, 130, 246, 0.1);
  color: var(--color-secondary);
}

.icon {
  width: 24px;
  height: 24px;
}

h3 {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.feature-item p {
  color: var(--color-text-muted);
  font-size: 0.95rem;
  line-height: 1.5;
}

.mission {
  font-size: 1.2rem;
  font-weight: 500;
  border-left: 4px solid var(--color-primary);
  padding-left: 1.5rem;
  font-style: italic;
  color: white;
}

/* Visuals */
.visual-col {
  display: flex;
  justify-content: center;
  position: relative;
}

.circle-graphic {
  position: relative;
  width: 400px;
  height: 400px;
}

.circle {
  position: absolute;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.c1 {
  width: 100%;
  height: 100%;
  border-color: rgba(255, 87, 34, 0.3);
  animation: spin 20s linear infinite;
  border-width: 2px;
  border-style: dashed;
}

.c2 {
  width: 70%;
  height: 70%;
  top: 15%;
  left: 15%;
  border-color: rgba(59, 130, 246, 0.3);
  animation: spin-reverse 15s linear infinite;
}

.c3 {
  width: 40%;
  height: 40%;
  top: 30%;
  left: 30%;
  background: radial-gradient(circle, rgba(255, 87, 34, 0.2) 0%, rgba(255, 87, 34, 0) 70%);
  animation: pulse 4s ease-in-out infinite;
  border: none;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes spin-reverse {
  from { transform: rotate(360deg); }
  to { transform: rotate(0deg); }
}

@keyframes pulse {
  0%, 100% { transform: scale(1); opacity: 0.5; }
  50% { transform: scale(1.2); opacity: 0.8; }
}

@media (max-width: 900px) {
  .content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .feature-item {
    text-align: left;
  }
  
  .mission {
    padding-left: 0;
    border-left: none;
    border-top: 4px solid var(--color-primary);
    padding-top: 1.5rem;
  }
  
  .visual-col {
    display: none; /* Hide complex graphic on mobile if too crowded, or scale it down */
  }
}
</style>
