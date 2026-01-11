<script setup lang="ts">
import { Mail, MapPin, Phone } from 'lucide-vue-next';

const handleSubmit = (e: Event) => {
  e.preventDefault();
  alert('Thank you for your message! We will contact you shortly.');
};
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="contact-wrapper">
        <div class="contact-info">
          <h2 class="section-title">Get in Touch</h2>
          <p class="desc">Ready to ignite your project? Contact us today.</p>
          
          <div class="info-item">
            <Mail class="icon" />
            <span>hello@agninode.team</span>
          </div>
          <div class="info-item">
            <Phone class="icon" />
            <span>+81 (0) 3-1234-5678</span>
          </div>
          <div class="info-item">
            <MapPin class="icon" />
            <span>Tokyo, Japan</span>
          </div>
        </div>
        
        <form class="contact-form" @submit="handleSubmit">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" required placeholder="Your Name" />
          </div>
          
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" required placeholder="your@email.com" />
          </div>
          
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" rows="4" required placeholder="How can we help you?"></textarea>
          </div>
          
          <button type="submit" class="btn-submit">Send Message</button>
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
  padding: 6rem 2rem 2rem;
  background-color: #050608; /* Slightly darker than main bg */
}

.container {
  max-width: 1000px;
  margin: 0 auto;
}

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 4rem;
  margin-bottom: 6rem;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.desc {
  color: var(--color-text-muted);
  margin-bottom: 3rem;
}

.info-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
}

.icon {
  color: var(--color-primary);
  width: 20px;
  height: 20px;
}

/* Form Styles */
.contact-form {
  background-color: var(--color-surface);
  padding: 3rem;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.form-group {
  margin-bottom: 1.5rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}

input, textarea {
  width: 100%;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 8px;
  color: white;
  font-family: var(--font-body);
  transition: border-color 0.2s;
}

input:focus, textarea:focus {
  outline: none;
  border-color: var(--color-primary);
}

.btn-submit {
  width: 100%;
  padding: 1rem;
  background-color: var(--color-primary);
  color: white;
  border: none;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1rem;
  transition: background-color 0.2s;
}

.btn-submit:hover {
  background-color: var(--color-primary-hover);
}

.footer {
  text-align: center;
  color: var(--color-text-muted);
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  padding-top: 2rem;
  font-size: 0.9rem;
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
