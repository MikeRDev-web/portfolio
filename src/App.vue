<script setup>
import { RouterView } from 'vue-router'
import heading from './components/layod/heading.vue';
</script>

<template>
  <heading/>
  <main>
    <RouterView />
  </main>
</template>

<style scoped>
  main {
    width: 100%;
    margin-top: 60px;
    margin-bottom: 50px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
  }
</style>
