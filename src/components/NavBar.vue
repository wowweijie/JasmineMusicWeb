<script setup>
import { onMounted, ref } from "vue";
import { debounce } from "lodash";
import HelloWorld from "./HelloWorld.vue";

const stickyNav = ref(false);

function handleScroll(event) {
  // Any code to be executed when the window is scrolled
  // console.log("calling handleScroll");
  if (window.scrollY > 150){
    // console.log("sticky");
    stickyNav.value = true;
  }
  else {
    stickyNav.value = false;
  }
}

onMounted(() => {
  console.log(`App component is now mounted.`);
  const handleDebouncedScroll = debounce(handleScroll, 100);
  // window.addEventListener('scroll', handleDebouncedScroll);
  window.addEventListener('scroll', handleScroll);
});
</script>

<template>
  <div :class="{ sticky :  stickyNav }">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <RouterLink to="/about">Fees</RouterLink>
      <RouterLink to="/gallery">Gallery</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </div>
</template>

<style scoped>
a {
  text-decoration: none;
  color: #555555;
}

a.router-link-active {
  text-decoration: underline;
}

nav {
  font-size: 18px;
  text-align: center;
  margin-top: 2rem;
}

div.sticky {
  max-width: inherit;
  width: 100%;
  position: fixed;
  top: 0;
  z-index: 1;
  background: var(--jmw-bg-cream)
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 2rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
