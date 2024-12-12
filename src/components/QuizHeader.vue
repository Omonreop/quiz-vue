<script setup>
import { defineProps } from "vue";

const { questionPage, barPercentage } = defineProps([
  "questionPage",
  "barPercentage",
]);
</script>

<template>
  <header>
    <h1>Questions {{ questionPage }}</h1>
    <div class="bar">
      <div class="bar-progress" :style="{ width: barPercentage }"></div>
    </div>
  </header>
</template>

<style scoped>
header {
  margin-top: 20px;
}
header h4 {
  font-size: 30px;
}

.bar {
  width: 100%;
  height: 30px;
  border: 3px solid black;
  border-radius: 15px;
}

.bar-progress {
  height: 100%;
  width: 0%;
  background-color: rgb(103, 110, 110);
  border-radius: 12px;
}
</style>
