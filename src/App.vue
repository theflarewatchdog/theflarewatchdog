<script setup lang="ts">
import NavigationBar from "./components/NavigationBar.vue";
import ReportButton from "./components/ReportButton.vue";
</script>

<template>
  <div class="app-container">
    <NavigationBar />
    <div class="section-container">
      <section id="home" class="section-card">
        <header><h1>Be a watchdog</h1></header>
        <ReportButton />
      </section>
      <section id="about" class="section-card">
        <header><h1>Be a watchdog</h1></header>
        <ReportButton />
      </section>
    </div>
  </div>
</template>

<style scoped>
.app-container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.section-container {
  flex: 1;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.section-card {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
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
