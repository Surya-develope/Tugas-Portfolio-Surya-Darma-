<template>
  <div>
    
    <nav class="navbar fixed-top">
      <div class="container">
        <a class="brand" href="#">Surya Darma</a>

        <ul class="nav-links">
          <li v-for="section in sections" :key="section.id">
            <a
              :href="'#' + section.id"
              :class="{ active: activeSection === section.id }"
              @click="scrollTo(section.id)"
            >
              {{ section.name }}
            </a>
          </li>
        </ul>

        <button class="menu-toggle" @click="toggleMenu">
          <span :class="{ open: menuOpen }"></span>
        </button>
      </div>
    </nav>

    <Home id="home" />
    <About id="about" />
    <Skills id="skills" />
    <Projects id="projects" />
    <Contact id="contact" />
  </div>
</template>

<script>
import Home from "./views/Home.vue";
import About from "./views/About.vue";
import Skills from "./views/Skills.vue";
import Projects from "./views/Projects.vue";
import Contact from "./views/Contact.vue";

export default {
  components: { Home, About, Skills, Projects, Contact },
  data() {
    return {
      activeSection: "home",
      menuOpen: false,
      sections: [
        { id: "home", name: "Home" },
        { id: "about", name: "About" },
        { id: "skills", name: "Skills" },
        { id: "projects", name: "Projects" },
        { id: "contact", name: "Contact" }
      ]
    };
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  methods: {
    scrollTo(id) {
      document.getElementById(id).scrollIntoView({ behavior: "smooth" });
      this.menuOpen = false; // Tutup menu saat diklik (untuk mobile)
    },
    onScroll() {
      let scrollY = window.scrollY;
      this.sections.forEach((section) => {
        const element = document.getElementById(section.id);
        if (element.offsetTop <= scrollY + 200) {
          this.activeSection = section.id;
        }
      });
    },
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    }
  }
};
</script>

<style>

body {
 margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
  scroll-behavior: smooth;
  background-color: #121212;
  color: white;
  overflow: auto; 
  width: 100vw;
  height: 100vh;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(0, 0, 0, 0.9);
  padding: 15px 50px;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  box-shadow: 0px 4px 10px rgba(255, 255, 0, 0.5);
  transition: background 0.3s ease-in-out;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.brand {
  font-size: 24px;
  font-weight: bold;
  text-transform: uppercase;
  text-decoration: none;
  background: linear-gradient(90deg, #ffdd00, #ff8800);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  transition: 0.3s ease-in-out;
}

.brand:hover {
  text-shadow: 0px 0px 10px #ffdd00, 0px 0px 20px #ff8800;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 25px;
  margin-right: 5%; 
}

.nav-links li a {
  text-decoration: none;
  color: white;
  font-size: 1.2rem;
  font-weight: 500;
  transition: color 0.3s ease-in-out, transform 0.2s ease-in-out;
  position: relative;
}

.nav-links li a:hover {
  color: yellow;
  text-shadow: 0px 0px 10px yellow;
  transform: translateY(-2px);
}

.nav-links li a.active::after {
  content: "";
  width: 100%;
  height: 3px;
  background: yellow;
  position: absolute;
  bottom: -5px;
  left: 0;
  transition: transform 0.3s ease-in-out;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  position: relative;
  width: 30px;
  height: 30px;
}

.menu-toggle span {
  display: block;
  width: 30px;
  height: 3px;
  background: yellow;
  margin: 6px 0;
  transition: all 0.3s ease-in-out;
}

.menu-toggle span.open {
  transform: rotate(45deg);
  background: red;
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 60px;
    right: 0;
    background: rgba(0, 0, 0, 0.9);
    width: 100%;
    padding: 20px;
    text-align: center;
  }

  .menu-toggle {
    display: block;
  }
}
</style>
