<template>
  <div class="about">
    <div class="stars-container">
  <span class="stars"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
  <span class="shooting-star"></span>
</div>

    <div class="main-content">
      <header>
        <h1>Prajwal Saraf</h1><br><h2>Senior Full-Stack Engineer & API Architect</h2>
        <h3 class="subtitle">I build high-availability systems for global industries.</h3>
      </header>
      
      <div class="btn-group">
        <button class="primary-btn" @click="downloadCV">Download Technical CV</button>
        <div class="social-links">
          <a class="btn-link" href="https://www.linkedin.com/in/prajwal-saraf-271a80182/" target="_blank">LinkedIn</a>&nbsp;
          <a class="btn-link" href="https://github.com/prajwalsaraf" target="_blank">GitHub</a>
        </div>
      </div>
      
      <div class="grid-layout">
        <section class="info-block summary">
          <h2>Professional Summary</h2>
          <p>"With over 4 years of hands-on experience in the <strong>.NET ecosystem</strong>, I transition complex business requirements into scalable technical reality. I have engineered web content pipelines for high-traffic retail platforms and integrated intricate crew management logic for international airlines."</p>
        </section>

        <section class="info-block skills">
          <h2>Technical Skills</h2>
          <ul class="skills-list">
            <li><strong>Backend:</strong> .NET 8, C#, EF Core, REST APIs</li>
            <li><strong>Cloud:</strong> AWS (EC2, S3), Datadog, Crownpeak</li>
            <li><strong>Databases:</strong> SQL Server, Query Optimization</li>
          </ul>
        </section>
      </div><br><br>
      <h2>Personal Projects</h2>
    <ul>
      <li><strong>Personal Portfolio Website:</strong> Built with Vue.js, showcasing my projects and technical skills.</li>
      <li><strong>Open Source Contributions:</strong> Developed and maintained an open-source project called <i>Money-flow</i></li>
    </ul>
    </div>
  </div>
</template>

<script setup>
const downloadCV = () => {

  const cvUrl = '/Prajwal_Saraf_Resume.pdf'; 
  
  const link = document.createElement('a');
  link.href = cvUrl;
  link.setAttribute('download', 'Prajwal_Saraf_Resume.pdf');
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);

  console.log("CV Download initiated by recruiter.");
};
</script>
<style scoped>
/* 1. Reset and Full Screen Setup */
.about {
  position: fixed; /* Fixes to the viewport */
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%);
  color: #ffffff;
  font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
  overflow-y: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* 2. Bold & Poppy Headers */
h1 {
  font-size: clamp(2.5rem, 6vw, 4rem);
  font-weight: 900; /* Super Bold */
  text-transform: uppercase;
  line-height: 1;
  margin-bottom: 1rem;
  background: linear-gradient(to bottom, #fff 40%, #7eb6ff 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 0 15px rgba(126, 182, 255, 0.5));
}

h2 {
  font-size: 1.5rem;
  font-weight: 800;
  color: #7eb6ff;
  text-transform: uppercase;
  letter-spacing: 3px;
  margin-bottom: 1.5rem;
  border-left: 5px solid #7eb6ff;
  padding-left: 15px;
}

.subtitle {
  font-size: 1.2rem;
  color: #cbd5e0;
  font-weight: 300;
  letter-spacing: 1px;
}

/* 3. Layout and Content */
.main-content {
  position: relative;
  z-index: 10;
  width: 90%;
  max-width: 1100px;
  padding: 4rem 2rem;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(8px);
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  text-align: left;
}

.grid-layout {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 40px;
  margin-top: 3rem;
}

/* 4. Interactive Elements */
.btn-group {
  display: flex;
  align-items: center;
  gap: 20px;
  margin: 2.5rem 0;
  flex-wrap: wrap;
}

.primary-btn {
  padding: 15px 30px;
  background: #7eb6ff;
  color: #090a0f;
  border: none;
  border-radius: 8px;
  font-weight: 800;
  text-transform: uppercase;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
}

.primary-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(126, 182, 255, 0.4);
}

.btn-link {
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  border-bottom: 2px solid #7eb6ff;
  padding-bottom: 2px;
  transition: color 0.3s;
}

.btn-link:hover {
  color: #7eb6ff;
}

/* 5. Star Animation CSS */
.stars-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.stars {
  position: absolute;
  top: 0;
  left: 0;
  width: 2px;
  height: 2px;
  background: transparent;
  /* Massive box-shadow to create a galaxy of dots */
  box-shadow: 
    10vw 20vh #fff, 25vw 50vh #fff, 40vw 10vh #fff, 60vw 80vh #fff, 
    80vw 30vh #fff, 95vw 60vh #fff, 15vw 90vh #fff, 45vw 40vh #fff,
    70vw 20vh #fff, 30vw 70vh #fff, 55vw 5vh #fff, 85vw 85vh #fff;
  animation: twinkle 3s infinite alternate;
}

@keyframes twinkle {
  0% { opacity: 0.2; transform: scale(0.8); }
  100% { opacity: 0.8; transform: scale(1.2); }
}

/* 2. The Shooting Stars (The "Shower") */
.shooting-star {
  position: absolute;
  top: -10%; /* Start above the screen */
  width: 4px;
  height: 4px;
  background: #fff;
  border-radius: 50%;
  opacity: 0;
  box-shadow: 0 0 10px 2px rgba(255, 255, 255, 0.5);
  animation: meteor 4s linear infinite;
}

.shooting-star::before {
  content: '';
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 150px;
  height: 2px;
  background: linear-gradient(90deg, #fff, transparent);
}

@keyframes meteor {
  0% { 
    transform: rotate(315deg) translateX(0); 
    opacity: 0; 
  }
  5% { 
    opacity: 1; 
  }
  15% { 
    transform: rotate(315deg) translateX(-1000px); 
    opacity: 0; 
  }
  100% { 
    transform: rotate(315deg) translateX(-1000px); 
    opacity: 0; 
  }
}

/* 3. Staggered Random Positions & Timings */
.shooting-star:nth-child(1) { left: 20%; animation-delay: 0s; }
.shooting-star:nth-child(2) { left: 40%; animation-delay: 1.2s; animation-duration: 3s; }
.shooting-star:nth-child(3) { left: 60%; animation-delay: 2.5s; animation-duration: 5s; }
.shooting-star:nth-child(4) { left: 80%; animation-delay: 0.5s; }
.shooting-star:nth-child(5) { left: 10%; animation-delay: 3.8s; animation-duration: 6s; }
.shooting-star:nth-child(6) { left: 90%; animation-delay: 1.7s; }
.shooting-star:nth-child(7) { left: 35%; animation-delay: 4.2s; animation-duration: 3.5s; }
.shooting-star:nth-child(8) { left: 55%; animation-delay: 0.8s; }
.shooting-star:nth-child(9) { left: 75%; animation-delay: 2.1s; animation-duration: 4.5s; }
.shooting-star:nth-child(10) { left: 5%; animation-delay: 5.5s; }

/* Mobile Responsiveness */
@media (max-width: 768px) {
  .grid-layout { grid-template-columns: 1fr; }
  .about { align-items: flex-start; }
  .main-content { margin-top: 20px; padding: 2rem 1.5rem; }
}
</style>