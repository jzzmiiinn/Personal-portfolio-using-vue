<template>
  <section class="hero">
    <div class="hero-content">
      <h1>Hello, I'm Yasmin</h1>
      <p class="subtitle">Frontend Developer | UI/UX Designer </p>
      <p class="description">
        Building modern web experiences with Vue, Nuxt, and more. Explore my work below!
      </p>
      <div class="cta-buttons">
        <NuxtLink to="/projects" class="cta-button primary">View Projects</NuxtLink>
        <NuxtLink to="/contact" class="cta-button secondary">Get In Touch</NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
// No script needed
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  background: linear-gradient(to bottom, #1e1e2f, #2a2a4a);
  color: white;
  padding: 2rem;
}

.hero-content {
  max-width: 800px;
}

h1 {
  font-size: 4rem;
  margin-bottom: 1rem;
}

.subtitle {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  opacity: 0.9;
}

.description {
  font-size: 1.2rem;
  margin-bottom: 3rem;
  opacity: 0.8;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.cta-button {
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: bold;
  transition: all 0.3s;
}

.primary {
  background: #ff6b6b;
  color: white;
}

.primary:hover {
  background: #ff8787;
  transform: translateY(-3px);
}

.secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.secondary:hover {
  background: white;
  color: #1e1e2f;
}

@media (max-width: 768px) {
  h1 { font-size: 3rem; }
  .subtitle { font-size: 1.5rem; }
}
</style>