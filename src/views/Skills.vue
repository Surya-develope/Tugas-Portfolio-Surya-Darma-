<template>
    <div class="skills-container">
      <h1 class="title">My Skills</h1>
      <p class="subtitle">Technologies & tools I use to build awesome projects</p>
      
      <div class="skills-grid">
        <div class="skill-card" v-for="skill in skills" :key="skill.name">
          <div class="icon">{{ skill.icon }}</div>
          <h2>{{ skill.name }}</h2>
          <p>{{ skill.description }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        skills: [
          { name: "HTML & CSS", description: "Building beautiful and responsive web pages", icon: "🌐" },
          { name: "JavaScript", description: "Adding interactivity and functionality to websites", icon: "⚡" },
          { name: "Vue.js", description: "Developing modern frontend applications", icon: "🖥️" },
          { name: "Bootstrap", description: "Creating responsive designs with ease", icon: "🎨" }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* Styling utama */
  .skills-container {
    text-align: center;
    background: black;
    color: yellow;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px 20px;
    animation: fadeIn 1s ease-in-out;
  }
  
  /* Animasi saat masuk */
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }
  
  /* Judul */
  .title {
    font-size: 3rem;
    font-weight: bold;
    text-transform: uppercase;
    margin-bottom: 10px;
    letter-spacing: 2px;
  }
  
  /* Subtitle */
  .subtitle {
    font-size: 1.2rem;
    font-weight: 400;
    margin-bottom: 30px;
    color: gold;
  }
  
  /* Grid skills */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    width: 80%;
    max-width: 800px;
  }
  
  /* Kartu skill */
  .skill-card {
    background: rgba(255, 255, 0, 0.1);
    backdrop-filter: blur(10px);
    color: yellow;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(255, 255, 0, 0.3);
    text-align: center;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 2px solid yellow;
  }
  
  /* Efek hover */
  .skill-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 8px 20px rgba(255, 255, 0, 0.5);
    background: rgba(255, 255, 0, 0.3);
  }
  
  /* Ikon */
  .icon {
    font-size: 3rem;
    margin-bottom: 10px;
  }
  </style>
  