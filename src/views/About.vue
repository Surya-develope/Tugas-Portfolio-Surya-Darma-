<template>
  <div class="about-container">
    <div class="about-box">
      <h1 class="title">About Me</h1>
      <p class="description">
        Hi! I am <strong>Surya Darma</strong>, a web developer passionate about crafting interactive and engaging digital experiences.
        Currently, I am studying <strong>Informatics Engineering</strong> at <strong>Sultan Syarif Kasim University</strong>, where I am enhancing
        my skills in web development and emerging technologies.
      </p>
    </div>
  </div>
</template>

<style scoped>

.about-container {
  background-color: yellow;
  color: black;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
}

.about-box {
  background-color: black;
  color:white;
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
  max-width: 700px;
  animation: fadeIn 1s ease-in-out;
}

.title {
  font-size: 2.5rem;
  font-weight: bold;
  text-transform: uppercase;
  margin-bottom: 15px;
  letter-spacing: 2px;
}

.description {
  font-size: 18px;
  line-height: 1.6;
  font-weight: 500;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
