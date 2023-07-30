<script setup lang="ts">
import { gsap } from 'gsap';
import { onMounted, ref } from 'vue';

const name = ref<null>();
const jobTitle = ref<null>();

onMounted(() => {
  animation();
});

const animation = () => {
  const tl = gsap.timeline();
  tl.to(name.value, {
    y: 0,
    duration: 1,
  }).to(jobTitle.value, {
    y: 0,
    duration: 1,
  });
};

</script>

<template>
  <div class="banner-wrapper">
    <section>
      <hgroup>
        <h3>Hi, I am</h3>
        <div class="overflow-area">
          <h1 ref="name">
            MAY WENG
          </h1>
        </div>
        <div class="overflow-area">
          <h3 ref="jobTitle">
            Front End Web Developer
          </h3>
        </div>
      </hgroup>
      <div class="profile-wrap">
        <img
          class="profile"
          src="src/assets/profile.jpg"
          alt="may weng profile photo"
        >
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>

.banner-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 80vh;
  background-image: url('https://images.unsplash.com/photo-1678770249280-6cd8e2b64d0a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1673&q=80');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 79%;
  background-attachment: fixed;
}

section {
  display: flex;
  justify-content: center;
  width: 80%;
  max-width: 1000px;
}

hgroup {
  height: 100%;
  margin: auto 100px auto 0;

  h1, h3 {
    color: white;
  }

  h3 {
    font-size: 20px;
    font-weight: 400;
  }
  .overflow-area {
    overflow: hidden;

    h1 {
      font-size: 80px;
      letter-spacing: 12px;
      transform: translateY(150px);
    }

    h3 {
      font-size: 20px;
      font-weight: 400;
      transform: translateY(80px);
    }
  }
}

.profile-wrap {
  width: 200px;
  height: 200px;
  
  img {
    width: 100%;
    border-radius: 50%;
  }
}

</style>
