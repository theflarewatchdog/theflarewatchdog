<script setup lang="ts">
import NavigationBar from "./components/NavigationBar.vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Why from "./components/Why.vue";
</script>

<template>
  <div class="app-container">
    <NavigationBar class="navbar"/>
    <div class="section-container">
      <Home class="section-card" />
      <About class="section-card" />
      <Why class="section-card" />
    </div>
  </div>
</template>

<style scoped>
.app-container {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-rows: auto 1fr;
}

.navbar {
  grid-row: 1;
}

.section-container {
  grid-row: 2;
}

.section-card {
  width: 100%;
  height: 100vh;
  padding: 30px;
  box-sizing: border-box;
  scroll-snap-align: start;
}

.section-card:nth-of-type(2n) {
  background-color: #f0f0f0;
}

@media (max-width: 768px) {
  .section-card {
    height: auto;
    min-height: 100vh;
    padding: 10px;
  }
}
</style>
