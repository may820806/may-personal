<template>
  <div class="skill-wrapper">
    <h1>Skill</h1>
    <div class="skill-cards">
      <skillCard
        v-for="(item) in skillData"
        :key="item.title"
        :icon="item.icon"
        :title="item.title"
        :description="item.description"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import skillCard from './SkillCard.vue';
import type { ISkill } from '../interfaces/interfaces';
import gsap from 'gsap';

const tl = gsap.timeline();

tl.to('.skill-wrapper', {
  y: 0,
  // stagger: {
  //   amount: .4
  // },
  scrollTrigger: {
    trigger: '.exp-wrapper',
    start: 'top',
    end: 'bottom',
    pin: true,
  }
});

const skillData = ref<ISkill[]>([
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
    icon: '/icons/Javascript.png',
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
.skill-wrapper {
  position: absolute;
  top: 361vh;
  width: 100%;
  height: 100vh;
  padding-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-image: url("https://images.unsplash.com/photo-1538438253612-287c9fc9217e?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  h1 {
    margin-bottom: 30px;
    text-align: center;
    font-size: 50px;
    color: #2D4D42;
  }

  .skill-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 30px;
    max-width: 1000px;
  }
}

@media screen and (min-width: 914px) {
  .skill-wrapper {
    .skill-cards {
      justify-content: center;
    }
  }
}
</style>