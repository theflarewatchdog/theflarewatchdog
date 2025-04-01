<script setup lang="ts">
import ReportButton from "./components/ReportButton.vue";
</script>

<template>
  <div class="container">
    <header>
      <h1>The Flare Watchdog</h1>
    </header>
    
    <main>
      <ReportButton />
    </main>
  </div>
</template>

<style scoped>
.container {
  text-align: center;
  font-family: Arial, sans-serif;
  padding: 20px;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}
</style>
