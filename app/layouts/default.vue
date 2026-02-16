<template>
  <div class="app-layout">
    <Navbar />
    <NuxtPage />
    <Footer />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
</script>

<style scoped>
.app-layout {
  display: flex;
  flex-direction: column;
}

:deep(.page), 
:deep(main),
:deep(section) {
  flex: 1 0 auto;
}
</style>