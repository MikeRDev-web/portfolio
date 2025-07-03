<script setup>
import presentationCard from '@/components/Home/presentationCard.vue';
import technologies from '@/components/Home/technologies.vue';
import projects from '@/components/Home/projects.vue';
import contactForm from '@/components/Home/contactForm.vue';
</script>

<template>
    <div class="homeViwe">
        <presentationCard/>
        <h1 class="sectionTitle">Lenguajes y tecnologías que domino</h1>
        <technologies/>
        <h1 class="sectionTitle">Mis proyectos</h1>
        <projects/>
        <h1 class="sectionTitle">¡Contáctame!</h1>
        <contactForm/>
    </div>
</template>

<style scoped>
.homeViwe {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    width: 100vw;
    padding: 0 10px;
}
.sectionTitle {
    text-shadow: 0 0 10px var(--color-background);
    font-size: 120%;
    margin: 1rem auto;
    border-bottom: 5px solid var(--color-primary);
    padding-bottom: 1rem;
    width: 90%;
}
.warning {
    width: 90%;
    margin: 0 auto;
    background-color: var(--color-error);
    padding: 10px;
    text-align: center;
    border-radius: 10px;
    text-shadow: 0 0 10px black;
}
@media (min-width: 768px) {
    .sectionTitle {
        font-size: 2rem;
    }
    .warning {
        width: 60%;
    }
}
</style>
