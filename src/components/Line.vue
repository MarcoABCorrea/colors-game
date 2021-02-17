<template>
  <div class="line">
    <slot />
  </div>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  export default defineComponent({
    name: "Line",
  });
</script>

<style scoped>
  .line {
    display: flex;
    flex: 1;
    width: 60%;
    margin: auto;
  }
</style>
