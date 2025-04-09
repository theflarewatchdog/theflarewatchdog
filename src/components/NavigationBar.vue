<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from "vue";

defineProps({
  activeSection: {
    type: String,
    required: true,
  },
});

const sections = [
  { id: "home", label: "Home" },
  { id: "about", label: "About" },
  { id: "why", label: "Why" },
];

const scrollToSection = (id: string) => {
  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({
      behavior: "smooth",
      block: "start",
    });
  }
};

const scrollY = ref(0);

const handleScroll = () => {
  scrollY.value = window.scrollY;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

const navbarHeight = computed(() => {
  if (scrollY.value < 50) return "60px";
  if (scrollY.value > 100) return "40px";
  return `${60 - ((scrollY.value - 50) / 50) * 30}px`;
});
</script>

<template>
  <nav :style="{ height: navbarHeight }" class="navbar">
    <ul>
      <li v-for="section in sections" :key="section.id">
        <button 
        @click="scrollToSection(section.id)"
        :class="{ active: activeSection === section.id }">
          {{ section.label }}
        </button>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: rgba(0, 0, 0, 0.8);
  color: rgba(255, 255, 255, 0.87);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px 0px;
  transition: top 0.3s;
}

ul {
  padding: 0;
  list-style: none;
  display: flex;
  gap: 20px;
}

button {
  background: none;
  border: none;
  color: white;
  font-size: clamp(1rem, 3.0vw, 1.5rem);
  cursor: pointer;
  padding: 10px 15px;
}

button:hover {
  text-decoration: underline;
}

button.active {
  border: 2px solid rgba(255, 255, 255, 0.87);
  border-radius: 40px;
}
</style>
