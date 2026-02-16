<template>
  <div class="project-card">
    <div class="card-content">
      <h3>{{ project.title }}</h3>
      <p>{{ project.description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: Object
})
</script>

<style scoped>
.project-card {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  transition: all 0.35s ease;
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 18px 40px rgba(0,0,0,0.15);
}

.card-content {
  padding: 1rem 1.1rem 1.2rem;
  display: flex;
  flex-direction: column;
  gap: 0;
  text-align: center;
}

.card-content h3 {
  font-size: 1.25rem;
  color: #1e1e2f;
  font-weight: 600;
  margin: 0;
  margin-bottom: 0.4rem;
  padding: 0;
  line-height: 1;
}

.card-content p {
  font-size: 1rem;
  color: #555;
  margin: 0;
  padding: 0;
  line-height: 1.15;
}

.card-content > * {
  margin-block: 0;
}

@media (max-width: 600px) {
  .card-image {
    height: 160px;
  }
}

@media (min-width: 1400px) {
  .card-image {
    height: 220px;
  }
}
</style>
