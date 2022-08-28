<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="header">
    <h1 class="title">JASMINE KHOO</h1>
    <h3>Piano &nbsp;&nbsp; &centerdot; &nbsp;&nbsp; Violin</h3>
  </div>
</template>

<style scoped>
* {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
