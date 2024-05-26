<script setup>
import FirstPage from './components/FirstPage.vue'
import StartApply from './components/StartApply.vue'
import FrequentlyAsked from './components/FrequentlyAsked.vue'
import WebFooter from './components/WebFooter.vue'

const toTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};
</script>

<template>
  <div>
    <FirstPage /> 
    <FrequentlyAsked/>
    <StartApply/>
    <WebFooter/>
    <div class="to-top">
      <button @click="toTop">
        <img src="/up-arrow.jpg" alt="to-top" />
        <span class="tooltip-text">Scroll to top</span>
      </button>
    </div>
  </div>
</template>

<style scoped>
.to-top {
  position: fixed;
  bottom: 10px; /* Adjust as needed */
  left: 50px; /* Adjust as needed */
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
  width: 80px;
  background-color: #555;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
  position: absolute;
  bottom: 20px;
  left: 70%;
  transform: translateX(-50%);
  opacity: 0;
  transition: opacity 0.3s;
  font-size: 0.8rem;
}

.to-top:hover .tooltip-text {
  visibility: visible;
  opacity: 1;
}
</style>
