<script setup>
import { ref } from 'vue';

const toTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

const footerSections = ref([
  {
    logoSrc: '/src/assets/logo.svg',
    alt: 'logo design',
    content: `
      WorldQuant University is a leader in global education, delivering entirely free online offerings that expand access to studies and credentials in the data sciences.
    `,
    socialLinks: [
      { href: '#', src: '/src/assets/Facebook.svg', alt: 'Facebook' },
      { href: '#', src: '/src/assets/Twitter.svg', alt: 'Twitter' },
      { href: '#', src: '/src/assets/Linkedin.svg', alt: 'LinkedIn' },
      { href: '#', src: '/src/assets/Github.svg', alt: 'Github' }
    ]
  },
  {
    title: 'MScFE Program',
    links: [
      { text: 'Program Details', href: '#' },
      { text: 'MScFE Application', href: '#' },
      { text: 'Catalog', href: '#' }
    ]
  },
  {
    title: 'Applied Data Science Lab',
    links: [
      { text: 'Lab Details', href: '#' },
      { text: 'Lab Application', href: '#' }
    ]
  },
  {
    title: 'About',
    links: [
      { text: 'Our World', href: '#' },
      { text: 'Partnerships', href: '#' },
      { text: 'FAQ', href: '#' },
      { text: 'About WQU', href: '#' },
      { text: 'News', href: '#' },
      { text: 'Press', href: '#' },
      { text: 'Contact', href: '#' }
    ]
  },
  {
    title: 'Portals',
    links: [
      { text: 'Student Login', href: '#' },
      { text: 'Alumni Login', href: '#' }
    ]
  }
]);
</script>

<template>
  <footer>
    <section v-for="(section, index) in footerSections" :key="index" :class="['footer-section', { 'first-section': index === 0 }]">
      <div v-if="section.logoSrc">
        <img :src="section.logoSrc" :alt="section.alt" class="footer-logo" />
        <p v-html="section.content" class="content"></p>
        <nav v-if="section.socialLinks">
          <ul class="social-links">
            <li v-for="(link, index) in section.socialLinks" :key="index">
              <a :href="link.href">
                <img :src="link.src" :alt="link.alt" />
              </a>
            </li>
          </ul>
        </nav>
      </div>
      <div v-else>
        <h2>{{ section.title }}</h2>
        <nav>
          <ul>
            <li v-for="(link, index) in section.links" :key="index">
              <a :href="link.href">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </section>
    <div class="footer-bottom">
      <div class="to-top">
        <button @click="toTop">
          <img src="/up-arrow.jpg" alt="to-top" />
          <span class="tooltip-text">Scroll to top</span>
        </button>
      </div>
      <div class="copyright">
        <p>&copy; 2017-2024 WorldQuant University.</p>
      </div>
      <div class="footer-links">
        <ul>
          <li>
            <a href="#">Privacy Policy</a>
          </li>
          <li>
            <a href="#">Terms of Use</a>
          </li>
          <li>
            <a href="#">Cookie Policy</a>
          </li>
          <li>
            <a href="#">Accessibility</a>
          </li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background-color: #120f37;
  padding: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  text-align: left;
  color: #fff;
  width: 100%;
  margin-top: -26px;
  height: 100vh;
}

.footer-section {
  flex: 1;
  min-width: 200px;
  margin-left:20px; 
  padding: 10px;
  /* margin: 30px; */
}

.first-section {
  flex: 2;
  max-width: 400px;
  
}

.footer-section h2 {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.content {
  font-size: 1.2rem;
  margin-bottom: 10px;
  line-height: 1.5rem;
  font-weight: 300;
}

.footer-section ul li {
  margin: 15px 0;
}

.footer-section ul li a {
  text-decoration: underline;
  color: #eecc0dd0;
  display: inline-block;
  font-size: 0.9rem;
  letter-spacing: 1px;
  line-height: 5px;
}

.footer-section ul li a:hover {
  text-decoration: underline;
}

.footer-logo {
  max-width: 100%;
  height: auto;
  margin-bottom: 10px;
}

.social-links {
  display: flex;
  padding: 0;
}

.social-links li {
  padding: 0 5px;
}

.social-links li a {
  display: inline-block;
  margin-right: 10px;
}

.social-links li:last-child a {
  margin-right: 0;
}
.social-links li a img:hover {
  box-shadow: 0 0 10px 5px rgba(221, 192, 25, 0.5);
  transition: 0.5s;

}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin-top: 30px;
}

.to-top {
  position: relative;
}

.to-top button {
  background: none;
  border: none;
  cursor: pointer;
}

.to-top img {
  width: 30px;
  height: 30px;
  border-radius: 50%;
}

.tooltip-text {
  visibility: hidden;
  width: 100px;
  background-color: #555;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
  position: absolute;
  bottom: -30px;
  left: 80%;
  transform: translateX(-50%);
  opacity: 0;
  transition: opacity 0.3s;
  font-size: 0.8rem;
  z-index: 1;
}

.to-top button:hover .tooltip-text {
  visibility: visible;
  opacity: 1;
}

.footer-links {
  display: flex;
  margin-top: 20px;
 
}

.footer-links ul {
  list-style: none;
  padding: 0;
  display: flex;
  margin-right: 30px;
  
}

.footer-links ul li {
  padding: 0 10px;

}

.footer-links ul li a {
  text-decoration: underline;
  color: #fff;
  display: inline-block;
  font-size: 0.9rem;
  letter-spacing: 1px;
  line-height: 5px;
  transition: 0.5s;
  font-weight: 300;
 
}

.copyright {
  text-align: center;
  font-size: 0.9rem;
  color: #fff;
  font-weight: 300;
  margin-left: -37%;
}
@media (max-width: 768px) {
  footer {
    flex-direction: column;
    align-items: center;
    padding: 10px;
    height: auto;
    width: 110vw;
    margin-top: -6px;
    margin-left: -40px;
  }

  .footer-section {
    margin: 10px 0;
  }

  .footer-section:first-child {
    margin-top: 30px;
  }

  .footer-section:last-child {
    margin-bottom: 0;
  }

  .footer-bottom {
    flex-direction: column;
  }

  .to-top {
    margin-top: 20px;
  }

  .footer-links {
    margin-top: 20px;
    text-align: center;
  }

  .copyright {
    margin-left: 0;
  }
  .footer-section ul li a {
 
  font-size: 1rem;

}
.footer-section ul li a:hover{
  color: #8a7919;
  text-decoration: underline;
  
}
}

</style>
