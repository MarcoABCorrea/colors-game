<template>
  <Grid></Grid>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  import Grid from "./components/Grid.vue";

  export default defineComponent({
    name: "App",
    components: {
      Grid,
    },
  });
</script>

<style>
  body {
    margin: 0;
    height: 100vh;
    width: 100vw;
  }
  #app {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
</style>
