<script setup lang="ts">
import { ref, onMounted } from 'vue';

const name = ref('');

onMounted(() => {
  fetch('api/message')
    .then((resp) => resp.text())
    .then((text) => {
      name.value = text;
    })
    .catch((err) => {
      console.error(err);
    });
});
</script>

<template>
  <h1>{{ name }}</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
</template>

<style scoped></style>
