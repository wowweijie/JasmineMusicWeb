<script setup>
import { onMounted, ref } from "vue";
import { debounce } from "lodash";
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
</script>

<template>
  <div id="main-wrapper" @scroll.passive = "handleScroll">
    <div id="main-container">
      <Header />
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
#main-wrapper {
  justify-content: center;
  width: 100%;
}

#main-container {
  justify-content: center;
  max-width: 1024px;
  margin: auto;
  background-color: #faf2e8;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}
</style>
