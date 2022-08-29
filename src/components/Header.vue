<script setup>
import { onMounted, ref } from "vue";
import { debounce } from "lodash";
import HelloWorld from "./HelloWorld.vue";
import NavBar from "./NavBar.vue"
</script>

<template>
  <div class="wrapper">
    <HelloWorld />
    <NavBar />
  </div>
</template>

<style scoped>
* {
  justify-content: center;
  text-align: center;
  max-width: inherit;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
</style>
