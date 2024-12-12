<script setup>
import { defineProps } from "vue";
const { quizQuestionsLength, numberOfCorrectAnswer } = defineProps([
  "quizQuestionsLength",
  "numberOfCorrectAnswer",
]);
</script>

<template>
  <section class="result">
    <p>Score:</p>
    <h1>{{ numberOfCorrectAnswer }}/{{ quizQuestionsLength }}</h1>
    <RouterLink class="router" to="/">Go Back</RouterLink>
  </section>
</template>

<style scoped>
.result {
  margin-top: 20px;
  background-color: rgb(96, 96, 96);
  border: 1px solid;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 5px 0;
}
p {
  font-size: 25px;
  margin-bottom: 0;
}
h1 {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 160px;
  height: 80px;
  font-size: 80px;
  border: 1px solid black;
  background-color: rgb(0, 0, 0);
  color: white;
}
.router {
  text-decoration: none;
  border: 2px solid black;
  border-radius: 10px;
  padding: 20px;
  background-color: rgb(0, 0, 0);
  color: white;
}
.router:hover {
  background-color: rgb(95, 94, 94);
}
</style>
