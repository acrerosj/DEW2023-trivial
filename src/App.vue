<script setup>
import { ref } from 'vue';
import QuestionPanel from './components/QuestionPanel.vue';
import ScorePanel from './components/ScorePanel.vue';

const points = ref(0);
const questionsNumber = ref(0);

function updateScore(correct) {
  questionsNumber.value++;
  if (correct) points.value++;
}
</script>

<template>
  <header>
    <ScorePanel :points="points" :questionsNumber="questionsNumber" />
  </header>
  <main>
    <QuestionPanel @question-result="updateScore"/>
  </main>
</template>

<style scoped>
  
</style>
