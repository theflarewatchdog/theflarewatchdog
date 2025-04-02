<script setup lang="ts">
import ReportButton from "./ReportButton.vue";
</script>

<template>
  <section id="home">
    <header><h1>Does this sound familiar?</h1></header>
    <iframe 
      width="560" 
      height="315" 
      src="https://www.youtube.com/embed/videoseries?si=A_oNDdt3qeOVgigU&amp;list=PLdz3MBuce8onVLxxlcGvME5LL0d77uKYB" 
      title="YouTube video player" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
      referrerpolicy="strict-origin-when-cross-origin" 
      allowfullscreen
    ></iframe>
    <ReportButton />
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  gap: 30px;
  align-items: center;
  justify-content: center;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}
</style>