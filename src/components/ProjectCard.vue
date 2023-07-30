<template>
  <div
    class="project-card-wrapper"
  >
    <div
      :style="{backgroundImage: `url(${image})`, cursor: url ? 'pointer' : ''}"
      class="image"
      @click="toWebsite(url)"
    />
    <div class="text-group">
      <h3>
        {{ title }}
      </h3>
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { IProject } from '../interfaces/interfaces';

defineProps<IProject>();

const toWebsite = (url: string) => {
  if(url) {
    window.open(url, '_blank');
  }
};

</script>

<style lang="scss" scoped>

.project-card-wrapper {
  width: 31%;
  min-height: 400px;
  margin: 1%;
  border-radius: 10px;
  background-color: white;
  border-radius: 0 40px 0 40px;

  .image {
    width: 100%;
    height: 180px;
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: center;
    border-radius: 0 40px 0 40px;
    transition: all .3s;

    &:hover {
      background-size: 110%;
    }

    &:not(:hover) {
      background-size: 100%;
    }
  }
  .text-group {
    padding: 1.5rem;
    
    h3 {
      font-size: 26px;
      color: #2D4D42;
      margin-bottom: 12px;
    }
  }

}
</style>