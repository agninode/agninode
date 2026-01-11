<script setup lang="ts">
import { Mail, MapPin, Send } from 'lucide-vue-next';

const handleSubmit = (e: Event) => {
  e.preventDefault();
  alert('お問い合わせありがとうございます！内容を確認次第、ご連絡いたします。');
};
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info">
          <h2 class="section-title">お問い合わせ</h2>
          <p class="desc">
            プロジェクトのご相談や、技術的な課題について、<br>
            お気軽にお問い合わせください。
          </p>

          <div class="info-card">
            <div class="info-item">
              <div class="icon-box">
                <Mail class="icon" />
              </div>
              <div class="info-content">
                <span class="label">Email</span>
                <span class="value">eneisyou@agninode.team</span>
              </div>
            </div>

            <div class="info-item">
              <div class="icon-box">
                <MapPin class="icon" />
              </div>
              <div class="info-content">
                <span class="label">Office</span>
                <span class="value">〒903-0213<br>沖縄県中頭郡西原町千原59琉球大学</span>
              </div>
            </div>
          </div>
        </div>

        <form class="contact-form" @submit="handleSubmit">
          <h3 class="form-title">Send Message</h3>

          <div class="form-group">
            <label for="name">お名前</label>
            <input type="text" id="name" required placeholder="山田 太郎" />
          </div>

          <div class="form-group">
            <label for="email">メールアドレス</label>
            <input type="email" id="email" required placeholder="example@agninode.team" />
          </div>

          <div class="form-group">
            <label for="message">メッセージ</label>
            <textarea id="message" rows="4" required placeholder="ご相談内容をご記入ください"></textarea>
          </div>

          <button type="submit" class="btn-submit">
            送信する
            <Send class="icon-small" />
          </button>
        </form>
      </div>

      <footer class="footer">
        <p>&copy; {{ new Date().getFullYear() }} Agninode. All rights reserved.</p>
      </footer>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 8rem 2rem 2rem;
  background-color: transparent;
  /* Match body bg */
  position: relative;
}

/* Decoration */
.contact::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 200px;
  background: linear-gradient(180deg, var(--color-surface) 0%, rgba(0, 0, 0, 0) 100%);
  pointer-events: none;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
}

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
  margin-bottom: 6rem;
  align-items: start;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
}

.desc {
  color: var(--color-text-muted);
  margin-bottom: 3rem;
  font-size: 1.1rem;
}

.info-card {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 1.25rem;
  background-color: var(--color-surface);
  padding: 1.5rem;
  border-radius: 20px;
  box-shadow: var(--shadow-card);
  transition: transform 0.2s;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.info-item:hover {
  transform: translateY(-3px);
}

.icon-box {
  background-color: var(--color-secondary);
  width: 44px;
  height: 44px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  flex-shrink: 0;
}

.icon {
  width: 20px;
  height: 20px;
}

.info-content {
  display: flex;
  flex-direction: column;
}

.label {
  font-size: 0.8rem;
  font-weight: 700;
  text-transform: uppercase;
  color: var(--color-text-muted);
  margin-bottom: 0.25rem;
}

.value {
  font-weight: 700;
  color: white;
  font-size: 1rem;
}

/* Form Styles */
.contact-form {
  background-color: var(--color-surface);
  padding: 3rem;
  border-radius: 40px;
  box-shadow: var(--shadow-card);
  border: 1px solid rgba(255, 255, 255, 0.05);
  position: relative;
}

/* Playful decoration on form */
.contact-form::after {
  content: '';
  position: absolute;
  top: -10px;
  right: -10px;
  width: 100%;
  height: 100%;
  border-radius: 40px;
  background-color: var(--color-accent);
  z-index: -1;
  opacity: 0.3;
}

.form-title {
  margin-bottom: 2rem;
  font-size: 1.5rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 700;
  font-size: 0.95rem;
  color: white;
}

input,
textarea {
  width: 100%;
  padding: 1rem 1.25rem;
  background-color: #0A0B10;
  border: 2px solid rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  color: white;
  font-family: var(--font-main);
  font-weight: 500;
  font-size: 1rem;
  transition: all 0.2s;
}

input:focus,
textarea:focus {
  outline: none;
  background-color: #000;
  border-color: var(--color-secondary);
  box-shadow: 0 0 0 4px rgba(0, 229, 255, 0.1);
}

.btn-submit {
  width: 100%;
  padding: 1rem;
  background-color: var(--color-primary);
  color: white;
  border: none;
  border-radius: 16px;
  font-weight: 700;
  font-size: 1.1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  transition: all 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
  box-shadow: 0 4px 15px rgba(255, 107, 107, 0.3);
}

.btn-submit:hover {
  background-color: var(--color-primary-hover);
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(255, 107, 107, 0.4);
}

.btn-submit:active {
  transform: translateY(0);
}

.icon-small {
  width: 18px;
  height: 18px;
}

.footer {
  text-align: center;
  color: var(--color-text-muted);
  padding-top: 2rem;
  font-size: 0.9rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .contact-wrapper {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .contact-form {
    padding: 2rem;
  }
}
</style>
