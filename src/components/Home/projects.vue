<script setup>
import { ref } from 'vue';

import taskifyImg from '/src/assets/images/projects/taskify.webp';
import steamFinderImg from '/src/assets/images/projects/StreamFinder.webp';
import speedStarMarketImg from '/src/assets/images/projects/speedstarmarket.webp';
import atomicMusicImg from '/src/assets/images/projects/atomicmusic.webp';
import streamFinderVue from '/src/assets/images/projects/streamfindervue.webp';
import taskyfiVue from '@/assets/images/projects/taskyfy.webp';

//icons

import htmlIcon from '/src/assets/icons/technologies/html.svg';
import cssIcon from '/src/assets/icons/technologies/css.svg';
import jsIcon from '/src/assets/icons/technologies/javascript.svg';
import vueIcon from '/src/assets/icons/technologies/vue.svg';
import phpIcon from '/src/assets/icons/technologies/php.svg';

//suports
import mobil from '@/assets/icons/supports/mobil.svg';
import desktop from '@/assets/icons/supports/desktop.svg';

const projects = ref([
    {
        name: 'StreamFinder (Versión Vue.js)',
        image: streamFinderVue,
        githubLink: 'https://github.com/MikeRDev-web/StreamFinder-vue-version',
        linkWeb: 'https://skyblue-camel-733023.hostingersite.com/',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon,
            vueIcon
        ],
        supportMovil: true,
        supportDesktop: true
    },
    {
        name: 'Taskify (Versión Vue.js)',
        image: taskyfiVue,
        githubLink: 'https://github.com/MikeRDev-web/Taskify-Vue-version',
        linkWeb: 'https://darkcyan-ant-495840.hostingersite.com/',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon,
            vueIcon
        ],
        supportMovil: true,
        supportDesktop: true
    },
    {
        name: 'SpeedStarMarket',
        image: speedStarMarketImg,
        githubLink: 'https://github.com/MikeRDev-web/SpeedStarMarket',
        linkWeb: '',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon,
            vueIcon
        ],
        supportMovil: false,
        supportDesktop: true
    },
    {
        name: 'Taskify',
        image: taskifyImg,
        githubLink: 'https://github.com/MikeRDev-web/Taskify',
        linkWeb: '',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon
        ],
        supportMovil: false,
        supportDesktop: true
    },
    {
        name: 'StreamFinder',
        image: steamFinderImg,
        githubLink: 'https://github.com/MikeRDev-web/StreamFinder',
        linkWeb: '',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon
        ],
        supportMovil: false,
        supportDesktop: true
    },
    {
        name: 'AtomicMusic',
        image: atomicMusicImg,
        githubLink: 'https://github.com/MikeRDev-web/AtomicMusic',
        linkWeb: '',
        technologies: [
            htmlIcon,
            cssIcon,
            jsIcon,
            phpIcon
        ],
        supportMovil: false,
        supportDesktop: true
    }
])
</script>

<template>
    <div class="projects">
        <div class="project card" v-for="item in projects">
            <span class="project__name">{{ item.name }}</span>
            <img :src="item.image" :alt="item.name" class="project__img">
            <span>Tecnologías utilizadas</span>
            <span class="project__technologies">
                <img v-for="icon in item.technologies" :src="icon" alt="Icono" class="project__technologies-icon">
            </span>
            <div class="supportsBox">
                <span class="supportsBox__title">Diseño adapatado para</span>
                <span class="supportsBox__available">
                    <div class="supportsBox__available--item" v-show="item.supportMovil">
                        <img :src="mobil" alt="Mobil" class="supportsBox__available--item-ico">
                        <span class="supportsBox__available--item-name">Mobil</span>
                    </div>
                    <div class="supportsBox__available--item" v-show="item.supportDesktop">
                        <img :src="desktop" alt="Desktop" class="supportsBox__available--item-ico">
                        <span class="supportsBox__available--item-name">Desktop</span>
                    </div>
                </span>
            </div>
            <span class="project__link">
                <a :href="item.githubLink" target="_blank" class="project__link-btn">Codigo</a>
                <a :href="item.linkWeb" target="_blank" class="project__link-btn" :class="{disabled: item.linkWeb === ''}">Web</a>
            </span>
        </div>
    </div>
</template>

<style scoped>
.projects {
    width: 95%;
    height: max-content;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    padding: 0 20px;
    margin: 0 auto;
    gap: 1rem;
}

.project {
    width: 100%;
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
    border-radius: 10px;
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
    flex: 1;
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

.supportsBox {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.supportsBox__title {
    width: 100%;
    font-size: 100%;
    border-bottom: 1px solid var(--color-primary);
    padding-bottom: 5px;
}
.supportsBox__available {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 10px;
}
.supportsBox__available--item {
    min-width: max-content;
    height: 40px;
    display: flex;
    align-items: center;
    gap: 5px;
    border: 1px solid var(--color-neutral);
    padding: 3px 5px;
    border-radius: 5px;
}
.supportsBox__available--item-name {
   font-size: 90%;
   letter-spacing: 1px;
   font-weight: 200;
}
.supportsBox__available--item-ico {
    width: 20px;
    height: 20px;
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
