<template>
  <div
    class="exp-card-wrapper"
  >
    <h3>
      {{ title }}
    </h3>
    <h4>
      {{ subtitle }}
    </h4>
    <p v-html="content" />
  </div>
</template>

<script setup lang="ts">
import { IExp } from '../interfaces/interfaces';

defineProps<IExp>();

</script>

<style lang="scss" scoped>

.exp-card-wrapper {
  width: 50vw;
  padding: 1.8rem;
  border-radius: 10px;
  background-color: white;

  h3 {
    font-size: 26px;
    color: #2D4D42;
  }

  h4 {
    margin-bottom: 20px;
    font-weight: 500;
  }
}
</style>