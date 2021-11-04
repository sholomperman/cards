<script setup>
  import Card from './components/Card.vue';
  import Nav from './components/Nav.vue';
</script>

<template>
  <Nav />
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
    width: 100%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
  }
  @media (max-width: 1200px) {
    .app {
      grid-template-columns: repeat(3, 1fr);
    }
  }
  @media (max-width: 848px) {
    .app {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media (max-width: 565px) {
    .app {
      grid-template-columns: repeat(1, 1fr);
    }
  }
</style>
