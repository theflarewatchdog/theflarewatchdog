<script setup lang="ts">
const reportUrl = "https://report-pollution.ene.gov.on.ca/app/";
</script>

<template>
  <div class="report-container">
    <a :href="reportUrl" target="_blank" class="report-button">
      Report Your Concern
    </a>
  </div>
</template>

<style scoped>
.report-container {
  display: flex;
  justify-content: center;
}

.report-button {
  background-color: #d9534f;
  color: white;
  padding: 15px 25px;
  font-size: clamp(1rem, 3.0vw, 1.5rem);
  font-weight: bold;
  text-decoration: none;
  align-items: center;
  text-align: center;
  border-radius: 8px;
  box-shadow: 0px 6px 8px rgba(0, 0, 0, 0.2);
  transition: background-color 0.3s ease;
  cursor: pointer;
}

.report-button:hover {
  background-color: #c9302c;
}
</style>
