<template>
  <div
    class="project-wrapper"
  >
    <h1>Projects</h1>
    <section>
      <ProjectCard
        v-for="project in projectData"
        :key="project.title"
        :url="project.url"
        :image="project.image"
        :title="project.title"
        :description="project.description"
      />
    </section>
    <Email />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ProjectCard from './ProjectCard.vue';
import type { IProject } from '../interfaces/interfaces';

import Email from './Email.vue';

const projectData = ref<IProject[]>([
  {
    image: '/projects/pxbox.png',
    title: '全聯福利中心隔日達',
    description: '短期合作案，開發新功能與維護，使用Vue.js並有前台與管理後台，參與到前台分期付款功能、圖文版面前後台串接的開發等。',
    url: 'https://pxbox.es.pxmart.com.tw/'
  },
  {
    image: '/projects/grace.png',
    title: '玉山銀行資產配置系統',
    description: 'Vue.js. 使用chart.js繪製出各式會員投資產品分析圖表，並產出列印用頁面讓後端輸出PDF檔案。以及使用decimal.js處理原生javascript不能處理的精準小數運算。'
  },
  {
    image: '/projects/aeo.png',
    title: 'Aeolous',
    description: '機器人產品之RWD官方網站，採用Next.js框架。Recoil狀態管理、Splide.js、emailjs，部分手刻CSS動畫',
    url: 'https://aeolusbot.com/'
  },
  {
    image: '/projects/liff.png',
    title: '雙連教會LIFF App',
    description: 'LINE Front-end Framework (LIFF)可用LINE內建瀏覽器開啟，可直接向user索取LINE帳號資訊，user可配合條碼掃瞄API進行活動簽到，其他包含串接內部API進行代禱、新增編輯個人資料等。 ',
    url: 'https://liff.line.me/1657021052-XY76rjWq'
  },
  {
    image: '/projects/redpeak.png',
    title: 'Redpeak官方網站',
    description: '使用Vue.js(v2)平面設計公司RWD官方網站維護，畫面改版與新增頁面。',
    url: 'https://www.red-peak.com/'
  },
  {
    image: '/projects/sino1.png',
    title: '永豐銀行新理財網',
    description: '使用Next.js開發RWD網站與管理後台系統，檔案上傳下載、文字編輯器(TinyMCE)等功能。',
    url: 'https://www.sinotrade.com.tw/newweb/'
  },
  {
    image: '/projects/elktree.png',
    title: 'Elk Tree Studio',
    description: '主動向老闆提出由我執行UI設計並切版，使用Nuxt3。',
    url: 'http://elk-tree.studio/'
  },
  {
    image: '/projects/aiueo.png',
    title: '五十音練習機',
    description: '自製的五十音練習機。使用react(next.js), primereact UI.',
    url: 'https://aiueo-playground.vercel.app/'
  }
]);


</script>

<style lang="scss" scoped>

.project-wrapper {
  position: absolute;
  top: 440vh;
  flex-direction: column;
  display: flex;
  width: 100%;
  padding-top: 60px;
  margin-bottom: 60px;
  background-color: #f3f3f3;

  h1 {
    margin: 0 auto 30px auto;
    font-size: 50px;
    color: #2D4D42;
    text-align: center;
  }

  section {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    width: 80%;
    max-width: 1000px;
    margin: 0 auto 60px auto;
  }
}

</style>