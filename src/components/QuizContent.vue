<script setup>
import { defineProps } from "vue";

const emit = defineEmits(["selectOption"]);
const { question } = defineProps(["question"]);

function emitSelectedOption(option) {
  emit("selectOption", option);
}
</script>

<template>
  <section id="question-container">
    <h1 class="question-title">{{ question.text }}</h1>
  </section>
  <section id="options-container">
    <div
      class="option"
      v-for="option in question.answers"
      :key="option.id"
      @click="emitSelectedOption(option)"
    >
      <p class="option-label">{{ option.label }}</p>
      <div class="option-value">{{ option.text }}</div>
    </div>
  </section>
</template>

<style scoped>
#questions-container {
  margin-top: 30px;
}

.question-title {
  font-size: 30px;
  font-weight: bold;
  margin-bottom: 20px;
}

.option {
  display: flex;
  align-items: center;
  cursor: pointer;
}
/* .option:hover {
  background-color: aqua;
} */

.option-label {
  font-size: 20px;
  font-weight: bold;
  width: 50px;
  height: 50px;
  background-color: rgb(103, 110, 110);
  display: flex;
  align-items: center;
  justify-content: center;
}
.option-value {
  font-size: 20px;
  font-weight: bold;
  padding: 0 20px;
  background-color: rgb(188, 184, 184);
  width: 100%;
  height: 50px;
  display: flex;
  align-items: center;
}
.option-value:hover {
  background-color: rgb(103, 110, 110);
}
</style>
