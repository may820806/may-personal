<script setup lang="ts">
import gsap from 'gsap';

const tl = gsap.timeline();

tl.to('.about-wrapper', {
  y: 0,
  stagger: {
    amount: .4
  },
  delay: 5,
  scrollTrigger: {
    trigger: '.banner-wrapper',
    scrub: 1,
    start: 'top',
    end: 'bottom',
    pin: true,
  }
});
</script>

<template>
  <div class="about-wrapper">
    <section>
      <hgroup>
        <h1>About Me</h1>
        <h3>半路「回家」的工程師</h3>
      </hgroup>
      
      <div>
        <p>
          我是翁展眉 May， 亞東技術學院資管系畢業。畢業後因為對平面設計有興趣，從事電商美術設計類工作。<br>
        </p>
        <p>
          然而資訊管理系出身的我，在設計的旅程中發現，程式才能讓我找到自身的價值與成就感，毅然決定回歸程式設計的路，學習主流市場前端語言與框架。
        </p>
        <p>
          對於充滿未知的程式世界，我感到熱血，心流的狀態可以讓我保持正向思考，「成長心態」是我的人生態度，相信專心一志一定會達到更高的境界。
        </p>
        <p>
          平時工作內容為執行CSS切版、與後端溝通並串接API等工作，專案大多採用Vue與React兩個前端框架，在麋鹿樹工作室近三年的時間開發和維護約12個前端專案。
        </p>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>

.about-wrapper {
  position: absolute;
  top: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-image: url("https://images.unsplash.com/photo-1483794344563-d27a8d18014e?auto=format&fit=crop&q=80&w=2940&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D");
  background-size: cover;
}

section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 80%;
  max-width: 1000px;
  height: 450px;

  p {
    max-width: 600px;
    text-indent: 2rem;
    line-height: 1.8;
  }
}

hgroup {
  margin: 0 auto 20px auto;
  text-align: center;

  h1 {
    font-size: 50px;
    color: #2D4D42;
  }
}

@media screen and (max-width: 768px) {
  section {
    height: fit-content;
    margin: 60px 0;
  }
}

</style>

