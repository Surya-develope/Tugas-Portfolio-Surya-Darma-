<template>
  <div class="projects-container">
    <h1 class="title">My Projects</h1>
    <p class="subtitle">Some of the projects I have worked on</p>
    
    <div class="projects-grid">
      <div class="project-card" v-for="project in projects" :key="project.name">
        <div class="icon">{{ project.icon }}</div>
        <h2>{{ project.name }}</h2>
        <p>{{ project.description }}</p>
        <a href="#" class="btn">View Project</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        { name: "Portfolio Website", description: "A personal website to showcase my work.", icon: "💻" },
      ]
    };
  }
};
</script>

<style scoped>
.projects-container {
  text-align: center;
  background: yellow;
  color: black;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
}

.title {
  font-size: 3rem;
  font-weight: bold;
  text-transform: uppercase;
  margin-bottom: 10px;
  letter-spacing: 2px;
}

.subtitle {
  font-size: 1.2rem;
  margin-bottom: 30px;
  color: black;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  width: 80%;
  max-width: 1000px;
}

.project-card {
  background: black;
  color: yellow;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 2px solid black;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
  background: black;
}

.icon {
  font-size: 3rem;
  margin-bottom: 10px;
}

.btn {
  display: inline-block;
  margin-top: 10px;
  padding: 10px 15px;
  background: yellow;
  color: black;
  font-weight: bold;
  text-decoration: none;
  border-radius: 8px;
  transition: background 0.3s ease;
}

.btn:hover {
  background: gold;
}
</style>
