<script setup lang="ts">
import gsap from 'gsap';
import type { IExp } from '../interfaces/interfaces';
import ExpCard from './ExpCard.vue';
import { ref } from 'vue';

const experienceData = ref<IExp[]>([
  {
    title: '2015~2020',
    subtitle: '平面設計',
    content: '做過四間電商公司美編設計，曾參與過 <strong>3個嘖嘖百萬募資案</strong> 設計與攝影。'
  },
  {
    title: '2020/8~2021/1',
    subtitle: '泰嘉數位媒體 - 前端工程師',
    content: '大宇資訊子公司，產品為「遊戲基地Gamebase」，將php義大利麵程式碼轉為前後端分離 Vue2 + Nuxt.js 框架。串接內部API，第三方登入等。'
  },
  {
    title: '2021/1~Now',
    subtitle: '麋鹿樹工作室 - 前端工程師',
    content: '遠端接案公司，開發或維護過官方形象網站與後台管理系統約10多個專案。'
  }
]);


const tl = gsap.timeline();

tl.to('.exp-wrapper', {
  y: 0,
  delay: 5,
  scrollTrigger: {
    trigger: '.about-wrapper',
    start: 'top',
    end: 'bottom',
    pin: true,
  }
});

</script>

<template>
  <div class="exp-wrapper">
    <section>
      <h1>Experience</h1>
      <ExpCard
        v-for="(exp) in experienceData"
        :key="exp.title"
        class="exp-card"
        :title="exp.title"
        :subtitle="exp.subtitle"
        :content="exp.content"
      >
        <template #content="{item}">
          <ExpCard
            class="exp-card"
            :title="item.title"
            :subtitle="item.subtitle"
            :content="item.content"
          />
        </template>
      </ExpCard>
    </section>
  </div>
</template>

<style lang="scss" scoped>

.exp-wrapper {
  position: absolute;
  top: 200vh;
  width: 100%;
  min-height: 120vh;
  height: fit-content;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 60px 0;
  background-color: #f3f3f3;
}

section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 80%;
  max-width: 1000px;
}

h1 {
  margin: 0 auto 20px auto;
  font-size: 50px;
  color: #2D4D42;
  text-align: center;
}

.exp-card {
  margin: 20px;
  position: relative;
}

.exp-card:not(:first-of-type) {
  &::before {
    content: '';
    display: block;
    position: absolute;
    height: 30px;
    width: 3px;
    top: -30px;
    left: calc(50% + 8px);
    background-color: #000;
  }
}
.exp-card:not(:last-of-type) {
  &::after {
    content: '';
    display: block;
    position: absolute;
    bottom: -10px;
    left: 50%;
    width: 20px;
    height: 20px;
    background-color: white;
    border: 3px solid #2D4D42;
    border-radius: 50%;
  }
}

</style>
