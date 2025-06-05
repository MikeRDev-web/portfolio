<script setup>
import { ref } from 'vue';

import emailIco from '@/assets/icons/contacts/email.svg';
import phoneIcon from '@/assets/icons/contacts/phone.svg';
import locationIcon from '@/assets/icons/contacts/location.svg';

import linkedinIcon from '@/assets/icons/contacts/linkedin.svg';
import githubIcon from '@/assets/icons/contacts/github.svg';

const contactDetails = ref([
    {
        icon: emailIco,
        data: 'miguel.m.r.developer@gmail.com'
    },
    {
        icon: phoneIcon,
        data: '3316278001'
    },
    {
        icon: locationIcon,
        data: 'Guadalajara, Jal.'
    }
])

const social = ref([
    {
        icon: linkedinIcon,
        link: 'https://www.linkedin.com/in/miguel-angel-marmolejo-rodriguez-a04112225/',
        name: 'LinkedIn'
    },
    {
        icon: githubIcon,
        link: 'https://github.com/MikeRDev-web',
        name: 'Github'
    },
])

</script>


<template>
    <div class="card presentationCard">
        <span class="presentationCard__details">
            <img src="/src/assets/images/photos/myphoto.jpeg" alt="Mi foto" class="presentationCard__img">
            <span class="presentationCard__data">
                <h2 class="presentationCard__name">Miguel Angel Marmolejo Rodriguez</h2>
                <h3 class="presentationCard__vacant">FrontEnd Developer</h3>
            </span>
        </span>
        <span class="presentationCard__contact">
            <div class="contact" v-for="item in contactDetails">
                <img :src="`${item.icon}`" alt="icono" class="contact__icon">
                <span class="contact__data">{{ item.data }}</span>
            </div>
        </span>
        <span class="presentationCard__social">
            <div class="social" v-for="item in social">
                <img :src="`${item.icon}`" alt="Icono" class="social__ico">
                <a :href="`${item.link}`" target="_blank" class="social__link">{{ item.name }}</a>
            </div>
        </span>
        <span class="description">
            Soy un desarrollador frontend autodidacta con una fuerte pasión por crear experiencias web atractivas y funcionales. Domino tecnologías como HTML, CSS, JavaScript, Vue.js y PHP, que utilizo para transformar ideas en soluciones reales. Busco mi primera oportunidad laboral para seguir creciendo profesionalmente, aportar con entusiasmo y aprender de un equipo talentoso en el mundo del desarrollo web.
        </span>
    </div>
</template>

<style scoped>
.presentationCard {
    width: 90%;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 10px;
    margin: 0 auto;
    border-radius: 10px
}
.presentationCard__details {
    display: flex;
    gap: 10px;
    width: 100%;
    align-items: center;
}
.presentationCard__img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}
.presentationCard__data {
    width: calc(100% - 100px);
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 10px;
}
.presentationCard__name {
    font-size: 150%;
    font-weight: bold;
}
.presentationCard__vacant {
    font-size: 100%;
    font-weight: 400;
}
.presentationCard__contact {
    width: 100%;
    display: flex;
    align-items: start;
    flex-direction: column;
    gap: 10px;
}
.contact {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 100%;
}
.contact__icon, .social__ico {
    width: 20px;
    height: 20px;
}
.presentationCard__social {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
}
.social {
    display: flex;
    align-items: center;
    gap: 5px;
}
.social__link {
    font-size: 100%;
}
.description {
    width: 100%;
    height: max-content;
    font-size: 100%;
    text-align: center;
    font-weight: 400;
    border-top: 1px solid var(--color-secondary);
    padding-top: 10px;
}

@media (min-width: 768px) {
  .presentationCard {
    width: 70%;
    padding: 20px;
    gap: 20px;
  }

  .presentationCard__details {
    gap: 20px;
    width: 70%;
    display: flex;
  }

  .presentationCard__img {
    width: 150px;
    height: 150px;
  }

  .presentationCard__data {
    width: calc(100% - 150px);
    gap: 15px;
  }

  .presentationCard__name {
    font-size: 200%;
  }

  .presentationCard__vacant {
    font-size: 120%;
  }

  .presentationCard__contact {
    width: 100%;
    justify-content: space-between;
  }

  .contact {
    width: auto;
    gap: 15px;
    font-size: 110%;
  }

  .presentationCard__social {
    justify-content: flex-start;
  }

  .description {
    font-size: 100%;
    padding-top: 15px;
  }
}

</style>