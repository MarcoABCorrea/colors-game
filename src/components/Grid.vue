<template>
  <div class="grid">
    <Line :key="line" v-for="line in squares"> </Line>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  import Line from "./Line.vue";
  import Square from "./Square.vue";
  export default defineComponent({
    components: { Line, Square },
    name: "Grid",
    methods: {
      random(max: number): number {
        return Math.floor(Math.random() * max) + 1;
      },
    },
    data() {
      const squares = 2;
      return {
        squares,
      };
    },
  });
</script>

<style scoped>
  .grid {
    display: flex;
    flex-direction: column;
    height: 100%;
  }
</style>
