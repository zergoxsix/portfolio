<script setup lang="ts">
import Footer from './components/Footer.vue';
import Header from './components/Header.vue';

const isDarkMode = ref(false);

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.setAttribute('data-theme', isDarkMode.value ? 'dark' : 'light');
  localStorage.setItem('theme', isDarkMode.value ? 'dark' : 'light');
};

onMounted(() => {
  const savedTheme = localStorage.getItem('theme') || 'light';
  isDarkMode.value = savedTheme === 'dark';
  document.documentElement.setAttribute('data-theme', savedTheme);
});

provide('isDarkMode', isDarkMode);
provide('toggleDarkMode', toggleDarkMode);
</script>

<template>
  <div>
    <Header/>
    <NuxtLayout>
      <NuxtPage/>
    </NuxtLayout>
    <Footer/>
  </div>
</template>

<style>
:root {
  /* Light mode */
  --bg-primary: #f3f4f6;
  --bg-secondary: #ffffff;
  --text-primary: #0369a1;
  --text-secondary: #475569;
  --text-tertiary: #9ca3af;
  --accent: #0369a1;
  --accent-light: #06b6d4;
  --border: #e5e7eb;
  --shadow: rgba(0, 0, 0, 0.1);
}

[data-theme='dark'] {
  /* Dark mode */
  --bg-primary: #1a1a2e;
  --bg-secondary: #16213e;
  --text-primary: #06b6d4;
  --text-secondary: #cbd5e1;
  --text-tertiary: #64748b;
  --accent: #06b6d4;
  --accent-light: #22d3ee;
  --border: #334155;
  --shadow: rgba(0, 0, 0, 0.3);
}

* {
  transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease;
}
</style>
