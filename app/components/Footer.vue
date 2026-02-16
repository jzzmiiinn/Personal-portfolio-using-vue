<template>
  <footer class="site-footer">
    <div class="container">
      <p>&copy; 2026 Yasmin Ali. All rights reserved.</p>
      <div class="social-links">
        <a href="#" aria-label="GitHub">GitHub</a>
        <a href="#" aria-label="LinkedIn">LinkedIn</a>
        <a href="#" aria-label="Twitter">Twitter</a>
      </div> 
    </div>
  </footer>
</template>

<script setup>
// No script needed
</script>

<style scoped>
.site-footer {
  background: linear-gradient(160deg, #1e1e2f, #2a2a4a);
  color: white;
  padding: 3rem 2rem;
  text-align: center;
  font-size: 1rem;
  position: relative;
  overflow: hidden;
}

.site-footer::before {
  content: '';
  display: block;
  width: 60px;
  height: 4px;
  background: #ff6b6b;
  margin: 0 auto 2rem;
  border-radius: 2px;
}

.site-footer p {
  margin: 0;
  opacity: 0.9;
  letter-spacing: 0.5px;
}

.social-links {
  margin-top: 1.5rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
}

.social-links a {
  color: white;
  font-size: 1.5rem;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.social-links a:hover {
  color: #ff6b6b;
  transform: translateY(-3px);
  opacity: 1;
}

/* Responsive Footer */
@media (max-width: 768px) {
  .site-footer {
    padding: 2.5rem 1.5rem;
  }
  .site-footer::before {
    margin-bottom: 1.5rem;
  }
  .social-links {
    gap: 1rem;
  }
}
</style>

