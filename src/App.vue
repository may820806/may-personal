<script setup lang="ts">
import Banner from './components/Banner.vue';
import About from './components/About.vue';
import Experience from './components/Experience.vue';
import Skill from './components/Skill.vue';
import Projects from './components/Projects.vue';

import 'primevue/resources/primevue.min.css';
import 'primevue/resources/themes/saga-orange/theme.css';

</script>

<template>
  <Banner />
  <About />
  <Experience />
  <Skill />
  <Projects />
  <!-- <footer>
    <p>
      Copyright © 2023, May Weng may820806@gmail.com
    </p>
  </footer> -->
</template>

<style lang="scss" scoped>


footer {
  position: fixed;
  bottom: 0;
  right: 10px;
  width: 100.6%;
  height: 30px;
  padding-right: 10px;
  margin: auto;
  font-size: 14px;
  text-align: right;
  color: white;
  background-color: #2D4D42;
  
  p {
    line-height: 40px;
    width: 100%;
  }
}

@media screen and (max-width: 768px) {

  footer {
    width: 102%;
    padding-right: 0;
    
    p {
      text-align: center;
    }
  }
}
</style>
