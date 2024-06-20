<script setup>
import { ref } from 'vue';
import ButtonClick from './ButtonClick.vue';

// Importing SVGs
import MenuIcon from '../assets/menu.svg';
import CloseIcon from '../assets/close.svg';

const requirements = ref([
  'Beginner-level Python skills',
  'Familiarity with basic statistics',
  'A commitment to spend 10-15 hours per week on lecture videos, assignments, office hours, and individual study',
  'That students are at least 18 years of age'
]);

// Dropdown state
const isProgramDropdownOpen = ref(false);
const isFaqDropdownOpen = ref(false);
const isNavOpen = ref(false);

const toggleProgramDropdown = (state) => {
  isProgramDropdownOpen.value = state;
};

const toggleFaqDropdown = (state) => {
  isFaqDropdownOpen.value = state;
};

const toggleNav = () => {
  isNavOpen.value = !isNavOpen.value;
};
</script>
<template>
  <main>
    <header>
      <div class="header-container">
        <div class="logo">
          <a aria-label="Worldquant University Homepage" href="/">
            <img src="/logo.svg" alt="logo" />
          </a>
        </div>
        <div class="nav-container" :class="{ open: isNavOpen }">
          <nav class="secondary-nav">
            <a href="/news">News</a>
            <a href="/partnerships">Partnerships</a>
            <a href="/about">About</a>
          </nav>
          <nav class="primary-nav">
            <div 
              @mouseover="toggleProgramDropdown(true)" 
              @mouseleave="toggleProgramDropdown(false)"
              class="dropdown"
            >
              <h3><a href="/our-program">Our Program</a></h3>
              <div v-if="isProgramDropdownOpen" class="dropdown-content">
                <a href="/our-program/details">Program Details</a>
                <a href="/our-program/courses">Courses</a>
              </div>
            </div>
            <h3><a href="/our-world">Our World</a></h3>
            <div 
              @mouseover="toggleFaqDropdown(true)" 
              @mouseleave="toggleFaqDropdown(false)"
              class="dropdown"
            >
              <h3><a href="/faq">FAQ</a></h3>
              <div v-if="isFaqDropdownOpen" class="dropdown-content">
                <a href="/faq/general">General FAQ</a>
                <a href="/faq/admissions">Admissions FAQ</a>
              </div>
            </div>
          </nav>
        </div>
        <button @click="toggleNav" class="menu-icon">
          <img :src="isNavOpen ? CloseIcon : MenuIcon" alt="menu" />
        </button>
      </div>
    </header>

    <figure>
      <img src="../assets/front-image.jpeg" alt="front-page" class="front-img"/>
      <figcaption>
        <h2>
          Join the Applied Data <br /> Science Lab
        </h2>
        <ButtonClick />
      </figcaption>
    </figure>
    
    <article class="requirements">
      <div class="requirements-content">
        <h3>Program Requirements</h3>
        <div class="details">
          <p>
            The Applied Data Science Lab is a hands-on learning experience that accommodates learners with the right amount of foundational knowledge and a commitment to success.
          </p>
          <p>
            The Lab runs continuously, so you can start as soon as your application is accepted.
          </p>
          <p>Acceptance into the Applied Data Science Lab requires:</p>
          <ul>
            <li v-for="(requirement, index) in requirements" :key="index">{{ requirement }}</li>
          </ul>
          <p>This is the professional development opportunity that does not require any prior degrees or credentials.</p>
          <ButtonClick class="button"/>
        </div>
      </div>
    </article>
  </main>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=PT+Serif:ital,wght@0,400;0,700;1,400;1,700&display=swap');

.header-container{
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  padding: 20px;
  margin-bottom: -30px;
}
.logo{
  margin: -10px 0 0 -20px;
  width: 10px;
}
.nav-container {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.nav-container.open {
  display: flex;
  flex-direction: column;
  background-color: white;
  position: absolute;
  top: 0; /* Adjust based on your header height */
  right: 0;
  width: 100%;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
}

.menu-icon,
.close-icon {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  
}
.menu-icon  img,
 .close-icon img{
  width: 30px;
  height: 30px;

 }

.secondary-nav {
  margin: -40px 0 20px 0;
  display: flex;
  flex-direction: row;
  gap: 30px;
  position: relative;
}
.secondary-nav::after {
  content: "";
  position: absolute;
  bottom: -10px;
  right: 0;
  width: 150%;
  height: 0.2px;
  background-color: #c3c2d0;
  border-radius: 0 0 0 4px;
}

.primary-nav {
  display: flex;
  flex-direction: row;
  gap: 50px;
}

.primary-nav h3, .secondary-nav a {
  margin: 0;
}
.secondary-nav a {
  text-decoration: none;
  color: #c3c2d0;
  transition: color 0.3s;
  font-size: 0.9rem;
}
.primary-nav h3 a {
  text-decoration: none;
  color: #120f37;
  transition: color 0.3s;
  font-size: 1.7rem;
  font-weight: 600;
  font-family: "PT+Serif";
}

.primary-nav h3 a:hover, .secondary-nav a:hover {
  color: #ff0000;
}

.dropdown {
  position: relative;
}

.dropdown-content {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #ffffff;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  z-index: 1;
}

.dropdown-content a {
  color: #120f37;
  padding: 10px 20px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #f1f1f1;
}

header img {
  margin-bottom: 20px;
}

header button {
  background: none;
  border: none;
  cursor: pointer;
  margin-bottom: 20px;
}

header button svg {
  fill: #000;
}

nav li {
  margin-bottom: 10px;
}

nav a {
  color: #120f37;
  text-decoration: none;
}

header div[aria-labelledby="header-tags"] {
  display: flex;
  align-items: flex-start;
  flex-direction: row;
}

header div [aria-labelledby="header-tags"] ul {
  margin-top: 10px;
}

nav div[aria-labelledby="header-tags"] ul li a {
  color: #120f37;
  text-decoration: none;
}

header img {
  margin-top: -15px;
  width: 220px;
  height: auto;
}

figure {
  width: 103.2%;
  position: relative;
  margin: 18px 0 0 0;
  display: flex;
  justify-content: flex-end;
  margin-right: -25px;
}

.front-img {
  width: 75vw;
  height: auto;
  display: block;
}

figcaption {
  position: absolute;
  top: 50%;
  left: 10px;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

h2 {
  font-family: 'PT Serif';
  margin: 0 0 20px 0;
  font-size: 3rem;
  font-weight: 600;
  color: #120f37;
  text-align: left;
}

.requirements {
  margin-top: 60px;
  text-align: left;
}

.requirements-content {
  display: flex;
}

.requirements-content h3 {
  font-family: 'PT Serif';
  flex: 0 0 40%;
  font-size: 2.4rem;
}

.details {
  flex: 1;
  font-size: 1.1rem;
}

.requirements ul {
  list-style: none;
  padding: 0;
}

.requirements li {
  margin-bottom: 10px;
  padding-left: 20px;
  text-decoration: none;
  position: relative;
}

.requirements li:before {
  content: "•";
  position: absolute;
  left: 0;
  color: #120f37;
}

@media screen and (max-width: 1200px) {
  figcaption {
    left: 5px;
  }

  .requirements-content h3 {
    font-size: 1.8rem;
  }

  .details {
    font-size: 1rem;
  }
}

@media screen and (max-width: 992px) {
  figcaption {
    left: 0;
  }

  .front-img {
    width: 80vw;
  }

  .requirements-content h3 {
    font-size: 1.6rem;
  }

  .details {
    font-size: 0.95rem;
  }
}

@media screen and (max-width: 768px) {
  figcaption {
    position: static;
    text-align: left;
    margin-top: 20px;
  }

  figure {
    padding-bottom: 40px;
    width: 111vw;
    height: 123vh;
    margin: 20px -10px -30px -30px;
    display: block;
    background: #f3f0f0 linear-gradient(275deg, #EEEEF1 -2.49%, #ffffff 92.41%);
  }

  .front-img {
    width: 104.4%;
    margin: 20px -10px 0 -30px;
    display: block;
    object-fit: cover;
  }

  h2 {
    color: #120f37;
    font-size: 2.2rem;
    margin: 17rem 0 30px 70px;
  }

  .requirements-content {
    flex-direction: column;
  }

  .requirements-content h3 {
    flex: 0 0 auto;
    width: 100%;
  }

  .details {
    flex: 1;
    width: 100%;
  }
  .button {
    margin-top: 20px;
    margin: 0 auto;
  }
}

@media screen and (max-width: 600px) {
  .nav-container {
    display: none;
  }

  .menu-icon,
  .close-icon {
    display: block;
    
  }
  .menu-icon img,
  .close-icon img {
    width: 40px;
    height: 40px;
  }
  

  .nav-container.open {
    display: flex;
    flex-direction: column;
    background-color: white;
    position: absolute;
    top: 120px;
    right: 0;
    width: 50%;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 1;
  
  }

  .secondary-nav,
  .primary-nav {
    display: flex;
    flex-direction: column;
    gap: 20px;
    width: 100%;
  
  }

  .secondary-nav a,
  .primary-nav h3 a {
    display: block;
    text-align: center;
    width: 100%;
  }

  nav img {
    width: 180px;
  }

  .front-img {
    width: 100vw;
    margin: 20px 0;
  }

  h2 {
    font-size: 2rem;
    margin: 10rem 0 20px 2rem;
  }

  .requirements-content h3 {
    font-size: 1.5rem;
   
  }

  .details {
    font-size: 1rem;
    margin: 0 0 8px 10px;
  }

  .requirements li {
    
    padding-left: 15px;
    
  }
}

@media screen and (max-width: 400px) {
  h2 {
    font-size: 1.8rem;
    margin: 8rem 0 20px 10px;
  }

  .requirements-content h3 {
    font-size: 1.2rem;
  }

  .details {
    font-size: 0.85rem;
  }

  .requirements li {
    margin-bottom: 6px;
    padding-left: 10px;
  }
}
</style>
