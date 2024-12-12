<script setup>
import { defineProps } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const { quiz } = defineProps(["quiz"]);

function goToQuiz() {
  router.push({ name: "quiz", params: { id: quiz.id } });
}
</script>

<template>
  <div class="card" @click="goToQuiz">
    <img :src="quiz.img" :alt="quiz.title" />
    <div class="card-body">
      <h2 class="card-title">{{ quiz.title }}</h2>
      <p class="card-desc">{{ quiz.questions.length }} Questions</p>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin: 10px;
  width: 270px;
  overflow: hidden;
  transition: transform 0.2s;
  cursor: pointer;
}
.card:hover {
  transform: scale(1.05);
}
.card img {
  width: 100%;
  height: auto;
  object-fit: cover;
}
.card-body {
  padding: 20px;
}
.card-title {
  font-size: 1.5em;
  margin: 0 0 10px;
}
.card-desc {
  font-size: 1em;
  color: #666;
  margin: 0 0 20px;
}
</style>
