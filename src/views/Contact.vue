<template>
  <div class="contact-container">
    <h1 class="title">Contact Me</h1>
    <p class="subtitle">Let's connect and work together!</p>
    <div class="contact-form">
      <div class="input-group">
        <input type="text" placeholder="Your Name" />
      </div>
      <div class="input-group">
        <input type="email" placeholder="Your Email" />
      </div>
      <div class="input-group">
        <textarea placeholder="Your Message"></textarea>
      </div>
      <button class="send-button">Send Message</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactSection",
};
</script>

<style scoped>
.contact-container {
  text-align: center;
  background: black;
  color: yellow;
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
  margin-bottom: 10px;
}

.subtitle {
  font-size: 1.2rem;
  font-weight: 400;
  margin-bottom: 30px;
  color: gold;
}

.contact-form {
  background: rgba(255, 255, 0, 0.1);
  backdrop-filter: blur(10px);
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(255, 255, 0, 0.3);
  display: flex;
  flex-direction: column;
  width: 100%;
  max-width: 400px;
}

.input-group {
  margin-bottom: 15px;
}

.input-group input, 
.input-group textarea {
  width: 100%;
  padding: 12px;
  border: 2px solid yellow;
  background: transparent;
  color: yellow;
  font-size: 1rem;
  border-radius: 8px;
  outline: none;
  transition: all 0.3s ease;
}

.input-group input::placeholder,
.input-group textarea::placeholder {
  color: gold;
}

.input-group input:focus, 
.input-group textarea:focus {
  background: rgba(255, 255, 0, 0.2);
  box-shadow: 0 0 10px rgba(255, 255, 0, 0.5);
}

.send-button {
  padding: 12px;
  font-size: 1.2rem;
  font-weight: bold;
  background: yellow;
  color: black;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.send-button:hover {
  background: gold;
  transform: translateY(-3px);
  box-shadow: 0 4px 10px rgba(255, 255, 0, 0.5);
}
</style>
