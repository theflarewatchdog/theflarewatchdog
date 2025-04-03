<script setup lang="ts">
import NavigationBar from "./components/NavigationBar.vue";
import ReportButton from "./components/ReportButton.vue";
</script>

<template>
  <div class="app-container">
    <NavigationBar class="navbar"/>
    <div class="section-container">
      <section id="home">
        <header><h1 style="font-size: 2.5rem; margin-bottom: 20px;">
          Does this sound familiar?
        </h1></header>
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
      </section>
      
      <section class="text-content">
        <p>
          It's probably faimilar if you live in East Hamilton.
        </p>
        <p>
          Our community is familiar with the hum of industry.
        </p>
        <p>
          But that noise that stands out from the rest.
        </p>
      </section>

      <section id="about" class="text-content">
        <p>
          It is the sound that's heard when ArcelorMittal Dofasco's large gas flare is lit.
        </p>
        <p>
          It rings clearly throughout neighbourhoods more than 2 km away.
        </p>
      </section>

      <section id="why" class="text-content">
        <p>
          If you see the flare lit, record it!
        </p>
        <p>
          By reporting this noise with video evidence of the flare, you are helping our community send a clear message:
        </p>
        <ul>
          <li>We hear it.</li>
          <li>We're concerned about its impact on our sleep and well-being.</li>
          <li>We want to know whether it is compliant with the rules and regulations enforced on the rest of Hamilton's industry.</li>
          <li>We want the cause of the noise to be investigated and fixed.</li>
        </ul>
      </section>
    </div>
    <ReportButton class="fixed-report-button" />
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

.section-container section {
  width: 100%;
  height: 100vh;
  padding: 30px;
  box-sizing: border-box;
  scroll-snap-align: start;
  display: flex;
  flex-direction: column;
  gap: 30px;
  align-items: center;
  justify-content: center;
}

.section-container section:nth-of-type(2n) {
  background-color: #f0f0f0;
}

.fixed-report-button {
  position: fixed;
  bottom: 100px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
}

@media (max-width: 768px) {
  .section-card {
    height: auto;
    min-height: 100vh;
    padding: 10px;
  }
}
</style>
