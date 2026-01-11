<script setup lang="ts">
import { ArrowRight, Sparkles } from 'lucide-vue-next';
</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="content">
        <div class="badge">
          <Sparkles class="badge-icon" />
          <span>沖縄から世界へ</span>
        </div>

        <h1 class="headline">
          あなたの<br>
          <span class="highlight">デジタルな可能性</span>に<br>
          火をつける
        </h1>

        <p class="subheadline">
          "Agni" (炎) のような情熱と、"Node" (技術) の確かなつながりで。<br>
          ビジネスの成長を加速させるITコンサルティング。
        </p>

        <div class="cta-group">
          <a href="#contact" class="btn btn-primary">
            旅を始める
            <ArrowRight class="icon" />
          </a>
          <a href="#services" class="btn btn-secondary">
            サービスを見る
          </a>
        </div>
      </div>
    </div>

    <!-- Playful Background Elements -->
    <div class="blobs">
      <div class="blob blob-1"></div>
      <div class="blob blob-2"></div>
      <div class="blob blob-3"></div>
    </div>
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
  background: transparent;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  position: relative;
  z-index: 10;
  text-align: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 50px;
  font-weight: 700;
  font-size: 0.9rem;
  color: var(--color-secondary);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  margin-bottom: 2rem;
  border: 1px solid rgba(0, 229, 255, 0.3);
  backdrop-filter: blur(5px);
}

.badge-icon {
  width: 16px;
  height: 16px;
}

.headline {
  font-size: 4.5rem;
  line-height: 1.1;
  margin-bottom: 2rem;
  color: white;
  text-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
}

.highlight {
  position: relative;
  color: var(--color-primary);
  -webkit-text-fill-color: var(--color-primary);
  display: inline-block;
}

/* Underline decoration */
.highlight::after {
  content: '';
  position: absolute;
  bottom: 10px;
  left: 0;
  width: 100%;
  height: 12px;
  background-color: rgba(255, 230, 109, 0.6);
  /* Yellow accent */
  z-index: -1;
  border-radius: 4px;
  transform: rotate(-1deg);
}

.subheadline {
  font-size: 1.25rem;
  color: var(--color-text-muted);
  max-width: 600px;
  margin: 0 auto 3rem;
  font-weight: 500;
}

.cta-group {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.icon {
  width: 20px;
  height: 20px;
}

/* Blobs */
.blobs {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  pointer-events: none;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.6;
}

.blob-1 {
  top: -10%;
  right: -5%;
  width: 500px;
  height: 500px;
  background-color: rgba(0, 229, 255, 0.15);
  /* Cyan */
  filter: blur(80px);
  animation: float 20s infinite alternate;
}

.blob-2 {
  bottom: -10%;
  left: -10%;
  width: 600px;
  height: 600px;
  background-color: rgba(255, 87, 34, 0.15);
  /* Orange */
  filter: blur(80px);
  animation: float 25s infinite alternate-reverse;
}

.blob-3 {
  top: 40%;
  left: 50%;
  width: 300px;
  height: 300px;
  background-color: rgba(255, 215, 0, 0.1);
  /* Gold */
  filter: blur(60px);
  transform: translate(-50%, -50%);
  animation: pulse 10s infinite;
}

@keyframes float {
  0% {
    transform: translate(0, 0);
  }

  100% {
    transform: translate(30px, 50px);
  }
}

@keyframes pulse {

  0%,
  100% {
    transform: translate(-50%, -50%) scale(1);
  }

  50% {
    transform: translate(-50%, -50%) scale(1.1);
  }
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
  }
}
</style>
