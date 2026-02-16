<template>
  <nav :class="{ scrolled: isScrolled }">
    <NuxtLink to="/" class="logo" @click="menuOpen = false">Yasmin</NuxtLink>
    
    <ul class="nav-links" :class="{ show: menuOpen }">
      <li><NuxtLink to="/" @click="menuOpen = false">Home</NuxtLink></li>
      <li><NuxtLink to="/about" @click="menuOpen = false">About</NuxtLink></li>
      <li><NuxtLink to="/projects" @click="menuOpen = false">Projects</NuxtLink></li>
      <li><NuxtLink to="/contact" @click="menuOpen = false">Contact</NuxtLink></li>
    </ul>
    
    <div class="hamburger" @click="menuOpen = !menuOpen">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen = ref(false)
const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.2rem 5%;
  background: rgba(30, 30, 47, 0.95);
  color: white;
  z-index: 1000;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: all 0.4s ease;
}

/* Scrolled */
nav.scrolled {
  background: #ffffff;
  padding: 1rem 5%;
  box-shadow: 0 4px 20px rgba(0,0,0,0.08);
}

/* Logo */
.logo {
  font-size: 1.9rem;
  font-weight: 700;
  color: #ff6b6b;
  text-decoration: none;
  letter-spacing: 1px;
}

/* Nav Links - Horizontal by default */
.nav-links {
  display: flex;       /* horizontal layout */
  gap: 2rem;           /* space between links */
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: white;
  text-decoration: none;
  font-weight: 600;
  font-size: 1.1rem;
  position: relative;
  transition: color 0.3s;
}

.nav-links a::after {
  content: '';
  display: block;
  width: 0;
  height: 2px;
  background: #ff6b6b;
  transition: width 0.3s;
  position: absolute;
  bottom: -4px;
  left: 0;
}

.nav-links a:hover::after,
.router-link-exact-active::after {
  width: 100%;
}

nav.scrolled .nav-links a {
  color: #1e1e2f;
}

nav.scrolled .nav-links a:hover,
nav.scrolled .router-link-exact-active::after {
  background: #ff6b6b;
}

/* Hamburger (mobile) */
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
}

.hamburger span {
  width: 28px;
  height: 3px;
  background: white;
  border-radius: 2px;
  transition: all 0.3s ease;
}

nav.scrolled .hamburger span {
  background: #1e1e2f;
}

/* Mobile Menu */
@media (max-width: 768px) {
  .nav-links {
    position: fixed;
    top: 0;
    right: -100%;
    height: 100vh;
    width: 70%;
    background: #1e1e2f;
    flex-direction: column;  /* vertical menu on mobile */
    gap: 2rem;
    justify-content: center;
    align-items: center;
    padding: 2rem;
    transition: right 0.3s ease;
    z-index: 999;
  }

  .nav-links.show {
    right: 0;
  }

  .nav-links a {
    font-size: 1.3rem;
  }

  .hamburger {
    display: flex;
  }

  nav.scrolled .nav-links {
    background: #ffffff;
  }

  nav.scrolled .nav-links a {
    color: #1e1e2f;
  }
}
</style>

