<script setup>
  import { useRouter } from "vue-router";

  const router = useRouter();
  const {quiz} = defineProps(['quiz']);

  const navigateToQuiz = () => {
    router.push(`/quiz/${quiz.id}`);
  };
</script>


<template>
  <div @click="navigateToQuiz" class="card">
    <img :src="quiz.img" alt="">
    <div class="card-text">
      <h2>{{ quiz.name }}</h2>
      <p>{{ quiz.questions.length }} questions</p>
    </div>
  </div>
</template>


<style scoped>
  .card {
    width: 310px;
    overflow: hidden;
    border-radius: 5px;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 30px;
    margin-right: 20px;
    cursor: pointer;
  }

  .card img {
    width: 100%;
    height: 200px;
    margin: 0;
  }

  .card .card-text {
    padding-inline: 20px;
    padding-bottom: 10px;
  }

  .card .card-text h2 {
    font-weight: bold;
  }
</style>