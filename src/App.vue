<script setup lang="ts">
import Banner from './components/Banner.vue';
import About from './components/About.vue';
import Experience from './components/Experience.vue';
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue';
import Email from './components/Email.vue';

import 'primevue/resources/primevue.min.css';
import 'primevue/resources/themes/saga-orange/theme.css';

</script>

<template>
  <Banner />
  <About />
  <Experience />
  <Skills />
  <Projects />
  <Email />
  <footer>
    <p>
      Copyright © 2023, May Weng may820806@gmail.com
    </p>
  </footer>
</template>

<style lang="scss" scoped>


footer {
  position: relative;
  right: 10px;
  width: 100.6%;
  height: 40px;
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
