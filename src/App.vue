<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";
import NavigationBar from "./components/NavigationBar.vue";
import ReportButton from "./components/ReportButton.vue";

const activeSection = ref("home"); // Track the currently visible section

onMounted(() => {
  const sections = document.querySelectorAll("section");
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          activeSection.value = entry.target.id;
        }
      });
    },
    { threshold: 0.6 } // Trigger when 60% of the section is visible
  );

  sections.forEach((section) => observer.observe(section));

  onUnmounted(() => {
    sections.forEach((section) => observer.unobserve(section));
  });
});
</script>

<template>
  <div class="app-container">
    <NavigationBar class="navbar" :active-section="activeSection" />
    <div class="section-container">
      <section id="home">
        <header><h1>Does this sound familiar?</h1></header>
          <div class="squishable-iframe-container" style="aspect-ratio: 650 / 350; max-width: 650px;">
            <iframe 
              src="https://www.youtube.com/embed/videoseries?si=A_oNDdt3qeOVgigU&amp;list=PLdz3MBuce8onVLxxlcGvME5LL0d77uKYB" 
              title="YouTube video player" 
              frameborder="0" 
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
              referrerpolicy="strict-origin-when-cross-origin" 
              allowfullscreen
            ></iframe>
          </div>
      </section>
      
      <section id="home2">
        <div class="normal-section">
          <p>
            It's probably faimilar if you live in East Hamilton.
          </p>
          <p>
            While it's not uncommon for our community to hear hum of industry, this noise stands out from the rest.
          </p>
        </div>
      </section>

      <section id="about">
        <div class="split-section">
          <div style="flex: 1;">
            <p>
              It's the sound that's heard when ArcelorMittal Dofasco's large gas flare is lit.
            </p>
            <p>
              It rings clearly throughout neighbourhoods more than 2 km away.
            </p>
          </div>
          <div class="squishable-iframe-container" style="flex: 1; aspect-ratio: 1; max-width: 600px;">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d23512.067873812797!2d-79.800605013315!3d43.26735596398069!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2zNDPCsDE2JzAxLjEiTiA3OcKwNDgnMTguMCJX!5e1!3m2!1sen!2sca!4v1743996679872!5m2!1sen!2sca" 
              width="600" 
              height="450" 
              style="border:0;" 
              allowfullscreen 
              loading="lazy" 
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </section>

      <section id="why">
        <div class="normal-section">
          <p>
            If the flare is lit, record it!
          </p>
          <p>
            By reporting the noise with video evidence, you are helping our community send a clear message:
          </p>
          <ul>
            <li>We hear it.</li>
            <li>We're concerned about its impact on our sleep and well-being.</li>
            <li>We want to know whether it is compliant with the rules and regulations enforced on the rest of Hamilton's industry.</li>
            <li>We want the cause of the noise to be investigated and fixed.</li>
          </ul>
        </div>
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

.section-container section {
  width: 100%;
  height: 100vh;
  padding: 30px;
  box-sizing: border-box;
  scroll-snap-align: start;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.section-container section:nth-of-type(2n) {
  background-color: #2e2e2e;
}

.normal-section {
  max-width: 650px;
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.normal-section p {
  text-align: center;
}

.split-section {
  display: flex;
  flex-direction: row;
  gap: 30px;
}

@media (max-width: 768px) {
  .split-section {
    flex-direction: column; /* Switch to vertical stacking */
  }
}

.fixed-report-button {
  position: fixed;
  bottom: 5vh;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
}

h1 {
  font-size: clamp(1.5rem, 5vw, 2.8rem);
  margin-bottom: 20px;
  text-wrap: normal;
}

p, ul {
  line-height: 1.4;
  font-size: clamp(1.1rem, 2.5vw, 1.5rem);
  color: rgba(255, 255, 255, 0.87);
}

.squishable-iframe-container {
  position: relative;
  width: 100%;
}

.squishable-iframe-container iframe {
  width: 100%;
  height: 100%;
}

@media (max-width: 768px) {
  .section-card {
    height: auto;
    min-height: 100vh;
    padding: 10px;
  }
}
</style>
