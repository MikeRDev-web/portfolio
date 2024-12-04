<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <header class="header card">
        <a href="#form" class="header__link">Contáctame</a>
    </header>
</template>

<style scoped>
.header {
    width: 100%;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: end;
    padding: 0 10px;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 9;
}
.header__link {
    text-decoration: none;
    background-color: var(--color-primary);
    padding: 5px;
    width: 150px;
    border-radius: 5px;
    text-align: center;
}
</style>