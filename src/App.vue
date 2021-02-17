<template>
  <Grid @gameOver="gameOver" v-if="!isGameOver"></Grid>
  <Card :title="title" v-if="isGameOver" @closeCard="isGameOver = false">
    <p>You clicked on {{ correct }} squares correctly!</p>
    <p>Elapsed time: {{ elapsedTime }}s</p>
  </Card>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  import Grid from "./components/Grid.vue";
  import Card from "./components/Card.vue";

  export default defineComponent({
    name: "App",
    components: {
      Grid,
      Card,
    },
    methods: {
      gameOver(start: number, correct: number): void {
        const now = new Date().getTime();
        const seconds = Math.ceil((now - start) / 1000);
        this.elapsedTime = seconds;
        this.correct = correct;
        this.isGameOver = true;
      },
    },
    data() {
      return {
        title: "Game Over!",
        isGameOver: false,
        elapsedTime: 0,
        correct: 0,
      };
    },
  });
</script>

<style>
  body {
    margin: 0;
    height: 100vh;
    width: 100vw;
    background-color: #f5f5f5;
  }

  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
</style>
