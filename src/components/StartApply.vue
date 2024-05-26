<script setup>
import { ref } from "vue";

const apply = ref("Ready to go?");
const imgSrc = ref("/motion picture4.jpg");
</script>

<template>
  <div class="container">
    <img :src="imgSrc" alt="Description of image" loading="lazy" />
    <aside class="apply-info">
      <div class="apply">{{ apply }}</div>
      <div class="apply-here">Start Application</div>
    </aside>
   
  </div>
</template>

<style scoped>
.container {
  position: relative;
  display: inline-block;
  margin-top: -20px;
  
  width: 102.3%;
}

img {
  display: block;
  margin: 20px auto;
  max-width: 100.9%;
  height: auto;
}

.apply {
  font-size: 3rem;
  font-weight: 600;
  text-align: center;
  color: #fff;
  margin-bottom: 20px;
}

.apply-here {
  font-size: 1.5rem;
  font-weight: 600;
  text-align: left;
  color: #fea65c;
  margin: -25px 0 20px 5px;
  cursor: pointer;
  text-decoration: underline;
}
.apply-here:hover {
  color: #db6e1b;
}
.apply-info {
  position: absolute;
  top: 17%;
  left: 13%;
  transform: translate(-50%, -50%);
  padding: 20px;
  border-radius: 10px;
  margin-left:20px; 
  
}

@media screen and (max-width: 1024px) {
  .container {
    width: 100%;
    margin-top: -20px;
  }

  img {
    max-width: 100%;
  }

  .apply {
    font-size: 2.5rem;
    margin-bottom: 15px;
  }

  .apply-here {
    font-size: 1.3rem;
    margin: -20px 0 15px 5px;
  }

  .apply-info {
    top: 20%;
    left: 15%;
    padding: 15px;
  }
}

@media screen and (max-width: 768px) {
  .container {
    width: 100%;
    margin: 0;
  }

  img {
    margin: 20px 0;
    max-width: 100%;
  }

  .apply {
    font-size: 2rem;
    margin-bottom: 10px;
  }

  .apply-here {
    font-size: 1.2rem;
    margin: -15px 0 10px 5px;
  }

  .apply-info {
    top: 25%;
    left: 20%;
    padding: 10px;
  }
}

@media screen and (max-width: 480px) {
  .container {
    width: 100%;
    margin: 0;
  }

  img {
    margin: 20px 0;
    max-width: 100%;
  }

  .apply {
    font-size: 1.5rem;
    margin-bottom: 5px;
  }

  .apply-here {
    font-size: 1rem;
    margin: -10px 0 5px 5px;
  }

  .apply-info {
    top: 30%;
    left: 25%;
    padding: 5px;
  }
}
</style>
