<!-- components/ContactSection.vue -->
<template>
  <section id="contact" class="contact-section">
    <div class="container">

      <form @submit.prevent="handleSubmit" class="contact-form">
        <div class="form-group">
          <div class="section-header">
            <h2>Contact Me</h2>
            <p class="section-subtitle">
              Feel free to reach out! I'm always open to discussing new opportunities, collaborations, or just chatting about tech.
            </p>
        </div>
          <label for="name">Name</label>
          <input
            id="name"
            v-model="name"
            type="text"
            placeholder="Your Name"
            required
          />

          <label for="email">Email</label>
          <input
            id="email"
            v-model="email"
            type="email"
            placeholder="your.email@example.com"
            required
          />

          <label for="message">Message</label>
          <textarea
            id="message"
            v-model="message"
            placeholder="Your message..."
            rows="6"
            required
          ></textarea>
        </div>

        <button type="submit" class="submit-button">
          Send Message
        </button>

        <p v-if="submitted" class="success-message">
          Message sent! I'll get back to you soon. 🎉
        </p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')
const submitted = ref(false)

function handleSubmit() {
  console.log({ name: name.value, email: email.value, message: message.value })
  submitted.value = true
  
  // Optional: Clear form after "send"
  // name.value = email.value = message.value = ''
  
  alert('Message sent! (Check console for details)')
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(to bottom, #1e1e2f, #2a2a4a);
  display: flex;
  align-items: center; /* Vertically centers on tall screens */
  padding: 0;
}

.container {
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

h2 {
  font-size: clamp(2.2rem, 5vw, 3rem);
  margin-top: 0;
  padding: 0;
  font-weight: 700;
  color: rgba(45, 41, 53, 0.9);
}

.section-subtitle {
  font-size: clamp(1rem, 2vw, 1.2rem);
  color: rgba(45, 41, 53, 0.9);
  max-width: 500px;
  margin: 0;
  padding: 0;
  line-height: 1;
}

.section-header {
  text-align: center;
  margin: 0; /* Reduced from 2rem */
  color: white;
}

.contact-form {
  background: white;
  padding-top: 0; 
  padding-bottom: 30px;
  margin: 25px;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.form-group {
  margin: 0; 
  padding-top: 0;
}

label {
  display: block;
  margin: 0;
  padding: 0;
  font-weight: 600;
  color: #1e1e2f;
  font-size: 1rem;
}

input,
textarea {
  width: 100%;
  padding: 0.9rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
  transition: all 0.3s ease;
  margin: 0;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #ff6b6b;
  box-shadow: 0 0 0 3px rgba(255, 107, 107, 0.1);
}

textarea {
  resize: vertical;
  min-height: 120px;
  margin: 0;
}

.submit-button {
  background: #ff6b6b;
  color: white;
  padding: 1rem;
  border: none;
  border-radius: 50px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  width: 100%;
  margin-top: 1rem;
  transition: all 0.3s ease;
}

.submit-button:hover {
  background: #ff8787;
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(255, 107, 107, 0.2);
}

.success-message {
  text-align: center;
  color: #28a745;
  font-weight: 600;
  margin-top: 1rem;
  font-size: 1rem;
}

@media (max-width: 480px) {
  .contact-section {
    padding: 5rem 1rem;
  }

  .contact-form {
    padding: 2rem 1.5rem;
  }
}
</style>