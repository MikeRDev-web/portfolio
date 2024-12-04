<script setup>
import { ref } from 'vue';

import taskifyImg from '/src/assets/images/projects/taskify.webp';
import steamFinderImg from '/src/assets/images/projects/StreamFinder.webp';
import speedStarMarketImg from '/src/assets/images/projects/speedstarmarket.webp';
import atomicMusicImg from '/src/assets/images/projects/atomicmusic.webp';

//icons

import htmlIcon from '/src/assets/icons/technologies/html.svg';
import cssIcon from '/src/assets/icons/technologies/css.svg';
import jsIcon from '/src/assets/icons/technologies/javascript.svg';
import vueIcon from '/src/assets/icons/technologies/vue.svg';
import phpIcon from '/src/assets/icons/technologies/php.svg';

const projects = ref([
    {
        name: 'Taskify',
        image: taskifyImg,
        githubLink: 'https://github.com/MikeRDev-web/Taskify',
        linkWeb: 'http://google.com',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon
        ]
    },
    {
        name: 'StreamFinder',
        image: steamFinderImg,
        githubLink: 'https://github.com/MikeRDev-web/StreamFinder',
        linkWeb: 'http://google.com',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon
        ]
    },
    {
        name: 'SpeedStarMarket',
        image: speedStarMarketImg,
        githubLink: 'https://github.com/MikeRDev-web/SpeedStarMarket',
        linkWeb: 'http://google.com',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon,
            vueIcon
        ]
    },
    {
        name: 'AtomicMusic',
        image: atomicMusicImg,
        githubLink: 'https://github.com/MikeRDev-web/AtomicMusic',
        linkWeb: 'http://google.com',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon
        ]
    }
])
</script>

<template>
    <div class="projects">
        <div class="project card" v-for="item in projects">
            <span class="project__name">{{ item.name }}</span>
            <img :src="item.image" :alt="item.name" class="project__img">
            <span class="project__technologies">
                <img v-for="icon in item.technologies" :src="icon" alt="Icono" class="project__technologies-icon">
            </span>
            <span class="project__link">
                <a :href="item.githubLink" target="_blank" class="project__link-btn">Codigo</a>
                <a :href="item.linkWeb" target="_blank" class="project__link-btn disabled">Web</a>
            </span>
        </div>
    </div>
</template>

<style scoped>
.projects {
    width: 100%;
    height: max-content;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    padding: 0 10px;
    margin: 0 auto;
    gap: 1rem;
}

.project {
    width: 90%;
    height: max-content;
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    gap: 10px;
}

.project__name {
    font-size: 110%;
    font-weight: 300;
    width: 95%;
    border-bottom: 1px solid var(--color-secondary);
    padding-bottom: 5px;
    text-align: center;
}

.project__img {
    width: 300px;
    height: 150px;
    border-radius: 3px;
}

.project__technologies {
    width: 90%;
    height: max-content;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    border: 1px solid var(--color-secondary);
    padding: 10px;
    border-radius: 5px;
}

.project__technologies-icon {
    width: 30px;
    height: 30px;
}

.project__link {
    width: 100%;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: end;
    gap: 0.5rem;
}

.project__link-btn {
    background-color: var(--color-primary);
    width: 90px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
    text-decoration: none;
    font-size: 90%;
}

.disabled {
    pointer-events: none;
    background-color: var(--color-neutral);
}

/* Media Query para pantallas grandes (pc) */
@media (min-width: 768px) {
    .projects {
        gap: 2rem;
    }

    .project {
        width: 30%;
        height: max-content;
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        border-radius: 15px;
        gap: 15px;
    }

    .project__name {
        font-size: 130%;
    }

    .project__img {
        width: 95%;
        height: 250px;
        margin: 0 auto;
    }

    .project__technologies {
        width: 100%;
        padding: 15px;
    }

    .project__technologies-icon {
        width: 40px;
        height: 40px;
    }

    .project__link {
        width: 100%;
        height: 60px;
        display: flex;
        align-items: center;
        gap: 1rem;
    }

    .project__link-btn {
        width: 120px;
        height: 50px;
        font-size: 100%;
    }
}
</style>
