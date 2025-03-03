<template>
  <nav class="navbar">
    <div class="logo">
      <a href="#">Surya Darma</a>
    </div>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Skills</a></li>
      <li><a href="#">Projects</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</template>

<style scoped>
/* Navbar Styling */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 50px;
  background: black;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  box-shadow: 0px 4px 10px rgba(255, 255, 0, 0.5);
}

/* Logo Styling */
.logo a {
  font-size: 1.8rem;
  font-weight: bold;
  text-transform: uppercase;
  color: yellow;
  text-decoration: none;
  position: relative;
  transition: 0.3s ease-in-out;
}

.logo a::after {
  content: "";
  width: 100%;
  height: 3px;
  background: yellow;
  position: absolute;
  bottom: -5px;
  left: 0;
  transform: scaleX(0);
  transition: transform 0.3s ease-in-out;
}

.logo a:hover::after {
  transform: scaleX(1);
}

.logo a:hover {
  color: white;
  text-shadow: 0px 0px 15px yellow;
}

/* Navbar Links */
.nav-links {
  list-style: none;
  display: flex;
  gap: 20px;
}

.nav-links li a {
  text-decoration: none;
  color: white;
  font-size: 1.1rem;
  transition: 0.3s ease-in-out;
}

.nav-links li a:hover {
  color: yellow;
  text-shadow: 0px 0px 10px yellow;
}

body, #app {
  background-color: black;
  color: white;
}
</style>
