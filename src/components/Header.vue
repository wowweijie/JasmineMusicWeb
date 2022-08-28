<script setup>
import { onMounted, ref } from "vue";
import { debounce } from "lodash";
import HelloWorld from "./HelloWorld.vue";

const stickyNav = ref(false);

function handleScroll(event) {
  // Any code to be executed when the window is scrolled
  // console.log("calling handleScroll");
  if (window.scrollY > 90){
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
  <div class="wrapper">
    <HelloWorld />

    <nav :class="{ sticky :  stickyNav }">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
    <b-navbar>
      <b-navbar-brand href="#">NavBar</b-navbar-brand>
    </b-navbar>
  </div>
</template>

<style scoped>
.wrapper {
  justify-content: center;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 18px;
  text-align: center;
  margin-top: 2rem;
}

nav.sticky {
  width: 100%;
  position: fixed;
  top: 0
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
