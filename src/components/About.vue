<script setup lang="ts">
import { Flame, Share2, Heart } from 'lucide-vue-next';
</script>

<template>
  <section id="about" class="about">
    <div class="container">
      <div class="content">
        <div class="text-col">
          <div class="tag">私たちの想い</div>
          <h2 class="section-title">Why <span class="highlight">Agninode</span>?</h2>
          <p class="description">
            社名である <strong>"Agninode"</strong> には、二つの大切な意味が込められています。
          </p>

          <div class="feature-list">
            <div class="feature-item">
              <div class="icon-box primary-box">
                <Flame class="icon" />
              </div>
              <div>
                <h3>Agni (炎・情熱)</h3>
                <p>何事にも情熱を持って取り組み、ビジネスを変革するエネルギーを象徴しています。</p>
              </div>
            </div>

            <div class="feature-item">
              <div class="icon-box secondary-box">
                <Share2 class="icon" />
              </div>
              <div>
                <h3>Node (結節点・つながり)</h3>
                <p>技術と人、現在と未来をつなぐ重要なハブ（拠点）としての役割を果たします。</p>
              </div>
            </div>
          </div>

          <div class="mission-card">
            <Heart class="mission-icon" />
            <p class="mission">
              私たちのミッションは、確かな技術力と熱い想いで、お客様のビジネスの可能性を最大化することです。
            </p>
          </div>
        </div>

        <div class="visual-col">
          <div class="composition">
            <div class="shape circle-main"></div>
            <div class="shape square-rotate"></div>
            <div class="shape pill"></div>
            <div class="shape dot dot-1"></div>
            <div class="shape dot dot-2"></div>
            <div class="shape dot dot-3"></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 8rem 2rem;
  background-color: var(--color-surface);
  /* Dark surface */
  border-radius: 60px 60px 0 0;
  /* Playful curve */
  position: relative;
  z-index: 5;
  box-shadow: 0 -10px 40px rgba(0, 0, 0, 0.5);
  border-top: 1px solid rgba(255, 255, 255, 0.05);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

.content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
}

.tag {
  display: inline-block;
  font-weight: 700;
  color: var(--color-primary);
  background-color: rgba(255, 87, 34, 0.15);
  /* Very light orange */
  padding: 0.5rem 1.25rem;
  border-radius: 50px;
  margin-bottom: 1.5rem;
  font-size: 0.9rem;
  border: 1px solid rgba(255, 87, 34, 0.3);
}

.section-title {
  font-size: 2.8rem;
  margin-bottom: 2rem;
  color: white;
  text-shadow: 0 0 15px rgba(255, 255, 255, 0.1);
}

.highlight {
  color: var(--color-primary);
  position: relative;
  z-index: 1;
}

.highlight::before {
  content: '';
  position: absolute;
  bottom: 0px;
  left: -5px;
  right: -5px;
  height: 15px;
  background-color: var(--color-accent);
  z-index: -1;
  border-radius: 4px;
  transform: rotate(-2deg);
  opacity: 0.7;
}

.description {
  color: var(--color-text-muted);
  font-size: 1.15rem;
  margin-bottom: 3rem;
}

.feature-list {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
  margin-bottom: 3rem;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 1.5rem;
}

.icon-box {
  width: 56px;
  height: 56px;
  border-radius: 18px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  font-size: 1.5rem;
}

.primary-box {
  background-color: rgba(255, 87, 34, 0.15);
  color: var(--color-primary);
  border: 1px solid rgba(255, 87, 34, 0.3);
}

.secondary-box {
  background-color: rgba(0, 229, 255, 0.15);
  color: var(--color-secondary);
  border: 1px solid rgba(0, 229, 255, 0.3);
}

.icon {
  width: 26px;
  height: 26px;
}

h3 {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
  font-weight: 800;
}

.feature-item p {
  color: var(--color-text-muted);
  font-size: 1rem;
  line-height: 1.6;
}

.mission-card {
  background-color: rgba(0, 0, 0, 0.3);
  padding: 2rem;
  border-radius: 24px;
  display: flex;
  gap: 1.5rem;
  align-items: flex-start;
  border: 2px dashed rgba(255, 255, 255, 0.1);
}

.mission-icon {
  color: var(--color-primary);
  width: 32px;
  height: 32px;
  flex-shrink: 0;
  filter: drop-shadow(0 0 5px var(--color-primary));
}

.mission {
  font-weight: 700;
  font-size: 1.1rem;
  color: white;
  margin: 0;
}

/* Playful Visuals */
.visual-col {
  display: flex;
  justify-content: center;
  position: relative;
}

.composition {
  position: relative;
  width: 400px;
  height: 400px;
}

.shape {
  position: absolute;
}

.circle-main {
  width: 300px;
  height: 300px;
  background-color: var(--color-secondary);
  border-radius: 50%;
  top: 50px;
  left: 50px;
  opacity: 0.2;
  filter: blur(40px);
}

.square-rotate {
  width: 180px;
  height: 180px;
  background-color: var(--color-accent);
  border-radius: 40px;
  top: 0;
  right: 40px;
  transform: rotate(15deg);
  opacity: 0.8;
  box-shadow: 10px 10px 0px rgba(0, 0, 0, 0.05);
  animation: float 6s ease-in-out infinite;
}

.pill {
  width: 120px;
  height: 250px;
  background-color: var(--color-primary);
  border-radius: 100px;
  bottom: 0;
  left: 20px;
  transform: rotate(-10deg);
  opacity: 0.9;
  box-shadow: -10px 10px 0px rgba(0, 0, 0, 0.05);
  animation: float-delayed 8s ease-in-out infinite;
}

.dot {
  width: 24px;
  height: 24px;
  border-radius: 50%;
  background-color: #2D3436;
}

.dot-1 {
  top: 20px;
  left: 20px;
}

.dot-2 {
  bottom: 100px;
  right: 0;
  background-color: var(--color-secondary);
}

.dot-3 {
  top: 150px;
  left: 160px;
  width: 16px;
  height: 16px;
  background-color: var(--color-primary);
  animation: pulse 3s infinite;
}

@keyframes float {

  0%,
  100% {
    transform: rotate(15deg) translate(0, 0);
  }

  50% {
    transform: rotate(12deg) translate(0, -20px);
  }
}

@keyframes float-delayed {

  0%,
  100% {
    transform: rotate(-10deg) translate(0, 0);
  }

  50% {
    transform: rotate(-8deg) translate(0, -15px);
  }
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.3);
  }

  100% {
    transform: scale(1);
  }
}

@media (max-width: 900px) {
  .content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .visual-col {
    display: none;
  }
}
</style>
