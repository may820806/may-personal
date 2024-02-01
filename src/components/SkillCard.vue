<template>
  <div class="skill-card-wrapper">
    <img :src="icon">
    <div class="texts">
      <h4>{{ title }}</h4>
      <p>{{ description }}</p>
    </div>
  </div>
</template>
<script setup lang="ts">
import type { ISkill } from '../interfaces/interfaces';

defineProps<ISkill>();

</script>

<style lang="scss" scoped>
.skill-card-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  min-width: 280px;
  width: 30%;
  height: 80px;
  padding: 20px;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  border-radius: 5px;
  background-color: white;

  img {
    width: 35px;
    margin-right: 5px;
    height: auto;
  }
}

.texts {
  width: 80%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;

  h4 {
    font-size: 25px;
  }
}

@media screen and (max-width: 960px) {
  .skill-card-wrapper {
    padding: 8px;
    height: 70px;
  }
  .texts {
    h4 {
      font-size: 20px;
    }

    p {
      font-size: 14px;
    }
  }
}
</style>