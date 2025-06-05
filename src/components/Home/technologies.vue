<script setup>
import { ref, onMounted } from 'vue';

//icons
import htmlIcon from '/src/assets/icons/technologies/html.svg';
import cssIcon from '/src/assets/icons/technologies/css.svg';
import jsIcon from '/src/assets/icons/technologies/javascript.svg';
import vueIcon from '/src/assets/icons/technologies/vue.svg';
import phpIcon from '/src/assets/icons/technologies/php.svg';
import gitIcon from '/src/assets/icons/technologies/git.svg';

const technologies = ref([
  {
    name: 'HTML',
    icon: htmlIcon,
  },
  {
    name: 'CSS',
    icon: cssIcon,
  },
  {
    name: 'JavaScript',
    icon: jsIcon,
  },
  {
    name: 'PHP',
    icon: phpIcon,
  },
  {
    name: 'Vue.js',
    icon: vueIcon,
  },
  {
    name: 'Git',
    icon: gitIcon,
  },
]);

const shuffleArray = (array) => {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
};

onMounted(() => {
  shuffleArray(technologies.value);
});
</script>

<template>
  <div class="technologies">
    <div class="technology card" v-for="item in technologies" :key="item.name">
      <img :src="item.icon" :alt="item.name" class="technology__icon" />
      <span class="technology__name">{{ item.name }}</span>
    </div>
  </div>
</template>

<style scoped>
.technologies {
    width: 90%;
    height: max-content;
    padding: 0 10px;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    gap: 5px;
}
.technology {
    width: 200px;
    height: 200px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
    border-radius: 10px;
    transform: scale(0.9);
    flex: 1;
}
.technology__icon {
    width: 60%;
    height: 60%;
}
.technology__name {
    font-size: 120%;
}
@media (min-width: 768px) {
  .technologies {
    width: 80%;
    margin: 0 auto;
    gap: 20px;
  }

  .technology {
    width: 200px;
    height: 200px;
    padding: 20px;
    gap: 15px;
    transform: scale(1);
    transition: transform 0.2s ease-in-out;
  }

  .technology:hover {
    transform: scale(1.05);
  }

  .technology__icon {
    width: 70%;
    height: 70%;
  }

  .technology__name {
    font-size: 140%;
  }
}

</style>