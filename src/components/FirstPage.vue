<script setup>
import { ref } from 'vue';
import ButtonClick from './ButtonClick.vue';

const requirements = ref([
  'Beginner-level Python skills',
  'Familiarity with basic statistics',
  'A commitment to spend 10-15 hours per week on lecture videos, assignments, office hours, and individual study',
  'That students are at least 18 years of age'
]);
</script>

<template>
  <main>
    <header>
      <div aria-labelledby="header-tags">
        <ul>
          <li><a href="">News</a></li>
          <li><a href="">Partnerships</a></li>
          <li><a href="">About</a></li>
        </ul>
      </div>
      <nav>
        <img src="/logo.svg" alt="logo" />
        <ul>
          <li><a href="">Our Programs</a></li>
          <li><a href="">Our World</a></li>
          <li><a href="">FAQ</a></li>
          <li><a href="">Apply</a></li>
          
        </ul>
      
      </nav>
    </header>
    
    <figure>
      <img src="/front-image.jpeg" alt="front-page" class="front-img"/>
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
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}


nav {
  display: flex;
  justify-content: space-between;
  align-items: flex-start; 
}

nav div[aria-labelledby="header-tags"] {
  display: flex;
  align-items: flex-start; 
  flex-direction:row;
}

nav div[aria-labelledby="header-tags"] ul {
  margin-top: 10px; 
}
nav div[aria-labelledby="header-tags"] ul li a{
  color: #120f37;
  text-decoration: none;
}

nav img {
  margin-top: -15px;
  width: 220px;
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
  margin: 0 0 20px 0;
  font-size: 2.5rem;
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
  flex: 0 0 40%;
  font-size: 2rem;
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
  color: #120f37; /* Adjust the color to your preference */
}

/* Media Queries */
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
  .button{
    margin-top: 20px;
    margin:0 auto;

  }
}

@media screen and (max-width: 576px) {
  nav img {
    width: 180px;
  }

  .front-img {
    width: 100vw;
    margin: 20px 0;
  }

  h2 {
    font-size: 2rem;
    margin: 10rem 0 20px 10px;
  }

  .requirements-content h3 {
    font-size: 1.5rem;
  }

  .details {
    font-size: 0.9rem;
  }

  .requirements li {
    margin-bottom: 8px;
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
<!-- I will come back and work on the nav tomorrow -->
