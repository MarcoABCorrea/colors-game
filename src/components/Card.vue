<template>
  <div class="card">
    <h2 class="title">{{ title }}</h2>
    <slot />
    <div class="action">
      <button @click="closeCard()">OK!</button>
    </div>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  export default defineComponent({
    name: "Card",
    props: {
      title: {
        type: String,
        required: true,
      },
    },
    methods: {
      closeCard(): void {
        this.$emit("closeCard");
      },
    },
  });
</script>

<style scoped>
  .card {
    display: flex;
    flex-direction: column;
    min-height: 45%;
    min-width: 30%;
    background-color: #fff;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    padding: 0 16px;
    font-family: Arial, Helvetica, sans-serif;
    transition-duration: 0.5s;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  }

  .title {
    align-self: center;
  }

  .action {
    margin: auto;
  }

  button {
    border: none;
    background-color: #665fc1;
    color: #fff;
    font-weight: 900;
    padding: 12px 24px;
    cursor: pointer;
    transition-duration: 0.2s;
  }

  button:hover {
    background-color: #8e87ea;
  }
</style>
