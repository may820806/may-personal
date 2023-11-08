<script setup lang="ts">
import { onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import EasePack from 'gsap/EasePack';
import Text from 'gsap/TextPlugin';

gsap.registerPlugin(ScrollTrigger, Text, EasePack);

onMounted(() => {
  animation();
});

ScrollTrigger.defaults({
  // reverse: 往回拉的時候標題會回來
  toggleActions: 'play none none reverse',
});

const animation = () => {
  const words = [' ', 'MAY WENG'];

  gsap.to('.hi', {
    y: 0,
  });

  gsap.to('.cursor', {
    opacity: 0,
    ease: 'power2.inOut',
    repeat: -1, //無限,
  });

  const masterTl = gsap.timeline({ delay: 0.1 });

  words.forEach((word) => {
    const tl = gsap
      .timeline({
        yoyo: true,
      })
      .to('.name', {
        duration: 1,
        text: word
      });
    masterTl.add(tl);
  });
};
</script>

<template>
  <div class="banner-wrapper">
    <section>
      <hgroup>
        <div class="hi-container">
          <h3 class="hi">
            Hi, I am
          </h3>
        </div>
        <div class="name-cursor">
          <h1 class="name" />
          <span class="cursor">_</span>
        </div>

        <div class="overflow-area">
          <h3 class="jobTitle">
            Front End Web Developer
          </h3>
        </div>
      </hgroup>
      <div class="profile-wrap">
        <img
          class="profile"
          src="/src/assets/photo.jpg"
          alt="may weng profile photo"
        >
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.banner-wrapper {
  position: absolute;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-image: url("https://images.unsplash.com/photo-1476231682828-37e571bc172f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1674&q=80");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50% 79%;
}

section {
  display: flex;
  justify-content: center;
  width: 80%;
  max-width: 1000px;
}

hgroup {
  min-width: 550px;
  height: 100%;
  margin: auto 100px auto 0;

  .hi-container {
    overflow: hidden;
  }

  .name-cursor {
    display: flex;
  }

  h1,
  h3,
  cursor {
    color: white;
    text-shadow: rgba(0, 0, 0, 0.16) 0px 10px 36px 0px,
      rgba(0, 0, 0, 0.06) 0px 0px 0px 1px;
  }

  .hi {
    display: block;
    min-height: 30px;
    transform: translateY(80px);
    font-size: 30px;
  }

  .name {
    font-size: 80px;
    letter-spacing: 12px;
  }

  .cursor {
    color: white;
    font-size: 80px;
  }
  .job-title {
    font-size: 20px;
    font-weight: 400;
  }
}

.profile-wrap {
  width: 200px;
  height: 200px;
  margin-bottom: 30px;

  img {
    width: 100%;
    border-radius: 50%;
  }
}

@media screen and (max-width: 768px) {
  section {
    flex-direction: column-reverse;
  }

  hgroup {
    margin: auto 0 auto 0;
  }

  .profile-wrap {
    width: 100px;
    height: 100px;

    img {
      width: 100%;
      border-radius: 50%;
    }
  }
}
</style>
