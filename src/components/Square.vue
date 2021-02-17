<template>
  <div class="square"></div>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  export default defineComponent({
    name: "Square",
  });
</script>

<style scoped>
  .square {
    margin: 5px;
    flex: 1 0 auto;
    cursor: pointer;
  }

  .bright {
    filter: brightness(150%);
  }
</style>
