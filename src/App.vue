<script setup>
  import Card from './components/Card.vue';
</script>

<template>
<div class="app">
  <Card />
</div>
</template>

<style>
  .app {
    box-sizing: border-box;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    width: 70%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    flex-wrap: wrap;
  }
</style>
