<script setup lang="ts">
import { Cpu, Cloud, Smartphone, Zap } from 'lucide-vue-next';

const services = [
  {
    icon: Cpu,
    title: 'IT戦略コンサルティング',
    description: 'ビジネスの目標達成に向けた最適なテクノロジー戦略を立案します。'
  },
  {
    icon: Cloud,
    title: 'クラウドアーキテクチャ',
    description: '拡張性が高くセキュアな、モダンなクラウド環境を構築します。'
  },
  {
    icon: Smartphone,
    title: 'DX推進サポート',
    description: 'レガシーシステムを刷新し、デジタル時代に即した変革を支援します。'
  },
  {
    icon: Zap,
    title: 'カスタム受託開発',
    description: 'パフォーマンスを重視した、お客様専用のソフトウェアを開発します。'
  }
];
</script>

<template>
  <section id="services" class="services">
    <div class="container">
      <div class="header">
        <h2 class="section-title">私たちの専門分野</h2>
        <p class="section-subtitle">デザインとテクノロジーで、ビジネスを次のステージへ。</p>
      </div>

      <div class="grid">
        <div v-for="(service, index) in services" :key="index" class="card">
          <div class="icon-wrapper" :class="`icon-${index}`">
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
  padding: 8rem 2rem;
  background-color: transparent;
  /* inherit body bg */
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

.header {
  text-align: center;
  margin-bottom: 5rem;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: white;
  position: relative;
  display: inline-block;
  text-shadow: 0 0 10px rgba(255, 255, 255, 0.2);
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 5px;
  right: -10px;
  width: 40px;
  height: 40px;
  background-color: var(--color-accent);
  border-radius: 50%;
  z-index: -1;
  opacity: 0.5;
}

.section-subtitle {
  color: var(--color-text-muted);
  font-size: 1.1rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 2.5rem;
}

.card {
  background-color: var(--color-surface);
  padding: 3rem 2rem;
  border-radius: 30px;
  transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  box-shadow: var(--shadow-card);
  border: 1px solid rgba(255, 255, 255, 0.05);
  text-align: left;
  position: relative;
  overflow: hidden;
}

.card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: var(--shadow-pop);
  border-color: var(--color-primary);
  background-color: var(--color-surface-hover);
}

.icon-wrapper {
  width: 70px;
  height: 70px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.card:hover .icon-wrapper {
  transform: rotate(10deg) scale(1.1);
}

/* Playful colors for icons - Dark Mode Adjusted */
.icon-0 {
  background-color: rgba(21, 101, 192, 0.2);
  color: #42A5F5;
}

.icon-1 {
  background-color: rgba(106, 27, 154, 0.2);
  color: #AB47BC;
}

.icon-2 {
  background-color: rgba(46, 125, 50, 0.2);
  color: #66BB6A;
}

.icon-3 {
  background-color: rgba(239, 108, 0, 0.2);
  color: #FFA726;
}

.icon {
  width: 32px;
  height: 32px;
}

.card-title {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.card-desc {
  color: var(--color-text-muted);
  font-size: 0.95rem;
  line-height: 1.8;
}
</style>
