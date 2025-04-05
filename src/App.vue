<script setup>
import { ref } from "vue";
import Home from "./pages/Home.vue";
import Contact from "./pages/Contact.vue";

const currentPage = ref("home");

function navigateTo(page) {
  currentPage.value = page;
}
</script>

<template>
  <div class="app-container">
    <header>
      <div class="logo-container">
        <a href="https://vite.dev" target="_blank">
          <img src="/vite.svg" class="logo" alt="Vite logo" />
        </a>
        <a href="https://vuejs.org/" target="_blank">
          <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
        </a>
      </div>
      <nav>
        <button
          @click="navigateTo('home')"
          :class="{ active: currentPage === 'home' }"
        >
          Home
        </button>
        <button
          @click="navigateTo('contact')"
          :class="{ active: currentPage === 'contact' }"
        >
          Contact
        </button>
      </nav>
    </header>

    <main>
      <component :is="currentPage === 'home' ? Home : Contact" />
    </main>
  </div>
</template>

<style scoped>
.app-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 1px solid #eaeaea;
}

.logo-container {
  display: flex;
  align-items: center;
}

nav {
  display: flex;
  gap: 10px;
}

nav button {
  background-color: #f3f3f3;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s;
}

nav button:hover {
  background-color: #e5e5e5;
}

nav button.active {
  background-color: #42b883;
  color: white;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
