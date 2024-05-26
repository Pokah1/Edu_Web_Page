<script setup>
import { ref } from 'vue';

// Define a reactive variable
const message = ref('Frequently Asked Questions');

const questions = ref([
  {
    question: 'How can I prepare for the Admissions Quiz?',
    answer: 'Before you can start the Applied Data Science Lab, you need to take a short Admissions Quiz to ensure you have a solid foundation on which you can build the skills taught in the offering. When taking the quiz, you should not use supplementary materials, so close your textbooks and any other browser windows. It is recommended that you have a pencil and paper ready in case you want to write out a problem.'
  },
  {
    question: 'How does the Lab work?',
    answer: 'The Applied Data Science Lab is divided into eight two-week projects and was designed to be completed in approximately 16 weeks. Following a prescribed sequence, students complete one project at a time. The projects range from exploring housing prices in Mexico to predicting air quality in Kenya. Students work with publicly available datasets, upon which they can develop larger portfolio projects. The curriculum is deployed on virtual machines, allowing you to...'
  },
  {
    question: 'What happens if I fail the Admissions Quiz?',
    answer: 'If you fail the Admissions Quiz for the Applied Data Science Lab, you have a second (and final) attempt after a 7-day cooling off period. If you fail a second time, you are unable to enroll in the Lab.'
  }
]);
</script>

<template>
  <main class="body">
    <h2>{{ message }}</h2>
    <ul class="faq-list">
      <li v-for="question in questions" :key="question.question" class="faq-item">
        <strong>{{ question.question }}</strong>
        <p>{{ question.answer }}</p>
      </li>
    </ul>
    <div class="button">
      <a href="#" class="faq-link">View Full FAQ</a>
    </div>
  </main>
</template>

<style scoped>
.body {
  width: 100%;
  margin: 50px 0 0 0;
  padding: 20px;
  background: #fec260 linear-gradient(114deg, #FEC260 74.89%, #FEA65C 100%);
 
}

h2 {
  font-family: 'Arial', sans-serif;
  color: #333;
  font-size: 3rem;
  text-align: left;
  margin-top: 20px;
  padding: 20px;
  border-radius: 10px;
   
}

.faq-list {
  list-style-type: none;
  padding: 0;
 
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  text-align:left ;

}

.faq-item {
  background-color: white;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  flex: 1 1 calc(33% - 20px); 
  box-sizing: border-box;
  display: flex;
  flex-direction: column;

}

.button {
  background-color: #4f3b80;
  border: 2px solid #4f3b80;
  border-radius: 100px;
  cursor: pointer;
  box-sizing: border-box;
  padding: 9px 24px;
  width: 15%;
  margin-top: 9%;
  margin-bottom: 4%;
}

.button a {
  color: #fff;
  text-decoration: none;
  font-size: 1rem;
 
}
.button:hover{
  background-color: #4f3b60;
  color: #4f3b80;
  border: 2px solid #4f3b80;
}

.faq-link {
  color: #fff;
  text-decoration: none;
  font-size: 1rem;
  font-family: 'Arial', sans-serif;
}

/* Media Queries */
@media screen and (max-width: 1024px) {
  .faq-item {
    flex: 1 1 calc(50% - 20px); /* Two columns */
  }


  .apply {
    font-size: 2.5rem;
  }

  .apply-here {
    font-size: 1.3rem;
  }

  .button {
    width: 25%;
    margin-top: 20px;
  }
}

@media screen and (max-width: 768px) {
  .faq-item {
    flex: 1 1 100%; /* Single column */
  }
  .body{
    width: 116.6%;
    margin: 30px -50px 0px -31px;
    padding: 30px;
  }

  .apply {
    font-size: 2rem;
  }

  .apply-here {
    font-size: 1.2rem;
  }

  .button {
    width: 40%;
    margin-top: 20px;
  }
  h2{
    font-size: 2rem;
  }
  .faq-item {
  background-color: white;
  padding: 20px;
  border: 1px solid #521b1b;
  border-radius: 10px;
  flex: 3 3 calc(2% - 20); 
  flex-direction: column;

}
.faq-list {
  list-style-type: none;
  padding: 0;
 width:85%;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  text-align:left ;

}

    }

@media screen and (max-width: 480px) {
  h2 {
    font-size: 2rem;
  }

  .faq-item {
    flex: 1 1 100%;
    padding: 10px;
  }

  .apply {
    font-size: 1.5rem;
  }

  .apply-here {
    font-size: 1rem;
  }

  .button {
    width: 60%;
    margin-top: 20px;
  }

  .faq-link {
    font-size: 0.9rem;
  }
}
</style>
