<template>
  <section id="about" class="about-section">
    <div class="container">
      <div class="about-grid">
        <div class="about-text">
          <h2>About Me</h2>
          <p>
            Hi! I’m Yasmin Ali, a Software Engineering student at Jimma University with a strong passion for web development and UI/UX design. I have solid experience in HTML, CSS, JavaScript, and React, creating responsive and interactive websites that are both functional and user-friendly.
            <br /><br />
            I enjoy crafting clean, intuitive designs and ensuring a smooth user experience, while also writing efficient, well-structured code. My projects reflect my dedication to bridging the gap between design and development.
            <br /><br />
            Currently, I am expanding my skills to become a full-stack developer, eager to learn backend technologies, database management, and deployment practices, so I can build complete web applications from scratch. I thrive on learning new technologies and turning ideas into real, working solutions.
          </p>
        </div>

        <div class="about-image">
          <img
            src="../assets/profile.jpg"
            alt="Yasmin Ali"
            class="profile-photo"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// No script needed
</script>

<style scoped>
.about-section {
  height: calc(100vh - 72px - 120px); /* full viewport minus navbar + footer estimate */
  padding-top: 27rem;                   /* extra space for navbar */
  padding-bottom: 25rem;                /* space above footer */
  padding-left: clamp(1.5rem, 5vw, 3rem);
  padding-right: clamp(1.5rem, 5vw, 3rem);
  background: linear-gradient(to bottom, #1e1e2f, #2a2a4a);
  display: flex;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  overflow: hidden;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: clamp(2rem, 4vw, 3rem);
  align-items: center;
  position: relative;
}

.about-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 2;
}

h2 {
  font-size: clamp(2rem, 4vw, 2.4rem);
  color: white;
  font-weight: 800;
  line-height: 1.2;
  letter-spacing: 0.5px;
}

p {
  font-size: clamp(0.95rem, 1.4vw, 1rem);
  margin-top: 0;
  padding-top: 0; 
  line-height: 1.5;
  color: white;
  text-align: justify;
  margin: 0;
}

/* IMAGE */
.about-image {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  z-index: 1;
}

.profile-photo {
  width: 100%;
  max-width: clamp(200px, 28vw, 320px);
  max-height: 50vh; /* smaller to avoid overlapping footer */
  object-fit: cover;
  border-radius: 20px;
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.12);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
}

.profile-photo:hover {
  transform: translateY(-6px) scale(1.02);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.15);
}

/* Large screen overlap */
@media (min-width: 1100px) {
  .profile-photo {
    margin-left: -2rem;
  }
}

/* TABLET */
@media (max-width: 900px) {
  .about-grid {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 1.5rem;
  }

  p {
    text-align: center;
  }

  .profile-photo {
    max-height: 35vh;
    margin-left: 0;
  }
}

/* SMALL MOBILE */
@media (max-width: 480px) {
  .about-section {
    padding-top: 6.5rem; /* enough to avoid navbar */
    padding-bottom: 5rem; /* space for footer */
    padding-left: 1rem;
    padding-right: 1rem;
  }

  h2 {
    font-size: 1.8rem;
  }

  p {
    font-size: 0.9rem;
  }

  .profile-photo {
    max-height: 28vh;
  }
}
</style>
