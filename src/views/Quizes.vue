<script setup>
import { ref, watch } from "vue";
import srcQuiz from "../data/quizes.json";
import QuizCard from "../components/QuizCard.vue";

const quizes = ref(srcQuiz);
const search = ref("");

watch(search, () => {
  quizes.value = srcQuiz.filter((quiz) => {
    return quiz.title.toLowerCase().includes(search.value.toLowerCase());
  });
});
</script>

<template>
  <header>
    <h1 id="title">Quiz</h1>
    <input v-model.trim="search" type="text" id="search-input" />
  </header>
  <section id="quiz-container">
    <QuizCard v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
  </section>
</template>

<style scoped>
header {
  margin-top: 30px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}
#title {
  font-weight: bold;
  margin-right: 30px;
}
#search-input {
  border: none;
  background-color: #c9c9c9a9;
  padding: 10px;
  border-radius: 5%;
}
#quiz-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
}
</style>
