src/components/ButtonClick.vue
<template>
  <button class="button" @click="buttonClick">{{ buttonText }}</button>
</template>

<script setup>
import { ref } from "vue";

const buttonText = ref("Start a New Application");

function buttonClick() {
  console.log("Start Application");
}
</script>

<style scoped>
.button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 1.1rem;
  font-weight: 400;
  color: #000000;
  background: #fec260 linear-gradient(114deg, #FEC260 74.89%, #FEA65C 100%);
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.button:hover {
  background: #d6b64c linear-gradient(114deg, #d8c278 74.89%, #d4b66e 100%);
}
</style>
