<script setup lang="ts">
import { shallowRef } from 'vue';
import CampoA from './CampoA.vue';
import CampoB from './CampoB.vue';

const currentComponent = shallowRef(CampoA);
</script>

<template>
  <div>
    <label>
      A
      <input type="radio" v-model="currentComponent" :value="CampoA" />
    </label>
    <label>
      B
      <input type="radio" v-model="currentComponent" :value="CampoB" />
    </label>

    <KeepAlive>
      <component :is="currentComponent" />
    </KeepAlive>
  </div>
</template>

<style scoped></style>
