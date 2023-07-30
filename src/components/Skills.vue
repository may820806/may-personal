<template>
  <div class="skills-wrapper">
    <h1>Skills</h1>
    <div class="skills-cards">
      <SkillsCard
        v-for="(item, index) in skillsData"
        :key="item.title"
        data-aos="flip-left"
        :data-aos-duration="1000"
        :data-aos-delay="index * 100"
        :icon="item.icon"
        :title="item.title"
        :description="item.description"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import SkillsCard from './SkillsCard.vue';
import type { ISkills } from '../interfaces/interfaces';

const skillsData = ref<ISkills[]>([
  {
    icon: '/icons/html.png',
    title: 'HTML',
    description: 'Semantic Elements'
  },
  {
    icon: '/icons/css.png',
    title: 'CSS',
    description: 'RWD, animation'
  },
  {
    icon: '/icons/javascript.png',
    title: 'Javascript',
  },
  {
    icon: '/icons/vue.png',
    title: 'Vue.js',
    description: 'Nuxt.js, Vite, Vuex, Pinia, Prime vue...'
  },
  {
    icon: '/icons/react.png',
    title: 'React',
    description: 'Next.js, MUI...'
  },
  {
    icon: '/icons/typescript.png',
    title: 'Typescript',
  },
  {
    icon: '/icons/scss.png',
    title: 'SASS/SCSS',
  },
  {
    icon: '/icons/git.png',
    title: 'GIT',
    description: 'Git flow'
  }
]);
</script>

<style lang="scss" scoped>
.skills-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 60px 0;

  h1 {
    margin-bottom: 30px;
    text-align: center;
    font-size: 50px;
    color: #2D4D42;
  }

  .skills-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 30px;
    max-width: 1000px;
  }
}

@media screen and (min-width: 914px) {
  .skills-wrapper {
    .skills-cards {
      justify-content: center;
    }
  }
}
</style>