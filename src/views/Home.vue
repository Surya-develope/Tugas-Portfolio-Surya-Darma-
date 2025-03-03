<template>
  <section class="home">
    <div class="container">

      <div class="title">
        <h1>{{ typingText }}</h1>
      </div>

      <div class="card">
        <div class="photo">
          <img src="../assets/profile.jpeg" alt="Profile Picture" />
        </div>

        <div class="text">
          <h2>Surya Darma - 12350110396</h2>
          <p>
            I am a student of Informatics Engineering at Sultan Syarif Kasim University. Passionate about technology and web development.
          </p>
          <a href="/CV.pdf" download class="download-btn">Download CV</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";

const typingText = ref("");
const fullText = "Welcome to My Portfolio";
const speed = 100;

onMounted(() => {
  let i = 0;
  function typeEffect() {
    if (i < fullText.length) {
      typingText.value += fullText.charAt(i);
      i++;
      setTimeout(typeEffect, speed);
    }
  }
  typeEffect();
});
</script>

<style scoped>

.home {
  background: linear-gradient(to bottom, black, #222);
  color: white;
  padding: 100px 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  flex-direction: column;
}

.title {
  text-align: center;
  margin-bottom: 20px;
}

.title h1 {
  font-size: 2.5rem;
  font-weight: bold;
  color: white;
  border-right: 3px solid white;
  display: inline-block;
  white-space: nowrap;
  overflow: hidden;
  animation: glow 1.5s infinite alternate;
}

@keyframes glow {
  from {
    text-shadow: 0px 0px 10px rgba(255, 255, 0, 0.8);
  }
  to {
    text-shadow: 0px 0px 20px rgba(255, 255, 0, 1);
  }
}

.card {
  background: rgba(255, 255, 0, 0.9);
  color: black;
  padding: 40px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0px 10px 30px rgba(255, 255, 0, 0.6);
  max-width: 750px; 
  display: flex;
  align-items: center;
  gap: 20px; 
  margin: 0 auto; 
}

.photo img {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
  border: 5px solid black;
  box-shadow: 0px 0px 20px rgba(255, 255, 0, 0.8);
}

.text {
  text-align: center; 
  flex: 1; 
}

.download-btn {
  background: black;
  color: yellow;
  font-size: 1rem;
  font-weight: bold;
  padding: 12px 24px;
  border: 2px solid yellow;
  cursor: pointer;
  border-radius: 8px;
  margin: 0 auto;
  display: inline-block;
  text-transform: uppercase;
  transition: all 0.3s ease-in-out;
  box-shadow: 0 4px 10px rgba(255, 255, 0, 0.5);
}

/* Efek hover */
.download-btn:hover {
  background:orange;
  color: black;
  border-color: black;
  box-shadow: 0 6px 15px rgba(255, 255, 0, 0.7);
  transform: scale(1.05);
}

/* Efek saat diklik */
.download-btn:active {
  transform: scale(0.95);
  box-shadow: 0 2px 8px rgba(255, 255, 0, 0.7);
}


</style>
