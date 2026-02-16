<template>
  <section id="projects" class="projects-section">
    <div class="container">
      <h2 class="section-header">Projects</h2>
      <div class="projects-grid">
        <ProjectCard 
          v-for="p in projects"
          :key="p.id"
          :project="p" />
      </div>
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  { 
    id: 1, 
    title: 'TODO LIST WITH CATEGORIES', 
    description: 'A productivity web app with nested categories, persistent local storage, and a clean, responsive UI.', 
  },
  { 
    id: 2, 
    title: 'COUNTDOWN MANAGER', 
    description: 'A countdown tracker with customizable titles and dates, built using JavaScript DOM manipulation and form validation.', 
  },
  { 
    id: 3, 
    title: 'CALCULATOR APP', 
    description: 'A simple, interactive React calculator for basic arithmetic operations with a clean, responsive design and efficient state handling.', 
  },
  { 
    id: 4, 
    title: 'WEATHER APP', 
    description: 'A responsive React app that displays real-time weather data using an external API. Includes search functionality and dynamic UI updates based on current conditions.', 
  }
]
</script>

<style scoped>
.projects-section {
  padding: 0;
  background: linear-gradient(to bottom, #1e1e2f, #2a2a4a);
  color: white;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 0; 
}

h2 {
  font-size: 3rem;
  color: white;
  margin: 0 0 1rem;
  font-weight: 700;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2.5rem;
}

/* Responsive */
@media (max-width: 968px) {
  h2 {
    font-size: 2.5rem;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .section-header {
    margin-bottom: 2rem;
  }
}

@media (max-width: 480px) {
  .projects-section {
    padding: 4rem 1.5rem;
  }
  
  .section-header {
    margin-bottom: 1.5rem;
  }
}
</style>