<template>
  <div class="grid">
    <Line :key="line" v-for="line in squares">
      <Square
        :class="{ bright: isBright(line, row) }"
        :style="{ backgroundColor }"
        :key="row"
        v-for="row in squares"
        @click="selectSquare(line, row)"
      ></Square>
    </Line>
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
      isBright(line: number, row: number): Boolean {
        return line === this.brightLine && row === this.brightRow;
      },
      selectSquare(line: number, row: number): void {
        if (this.isBright(line, row)) {
          this.squares++;
          this.brightLine = this.random(this.squares);
          this.brightRow = this.random(this.squares);
        } else {
          console.log("lose");
        }
      },
    },
    data() {
      const colors: string[] = [
        "#f3a683",
        "#f7b731",
        "#fa8231",
        "#e15f41",
        "#fc5c65",
        "#c44569",
        "#3dc1d3",
        "#40739e",
        "#546de5",
        "#574b90",
      ];
      const squares = 2;
      const brightLine: number = this.random(squares);
      const brightRow: number = this.random(squares);
      const colorIndex: number = this.random(colors.length - 1);
      return {
        squares,
        brightLine,
        brightRow,
        backgroundColor: colors[colorIndex],
      };
    },
  });
</script>

<style scoped>
  .grid {
    display: flex;
    flex-direction: column;
    height: 80%;
    width: 80%;
  }
</style>
