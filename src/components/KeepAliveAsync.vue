<script setup lang="ts">
import { ref, defineAsyncComponent } from 'vue';

const CampoA = defineAsyncComponent(() => import('./CampoA.vue'));
const CampoB = defineAsyncComponent(() => import('./CampoB.vue'));

const currentComponent = ref('CampoA');

const taps = {
  CampoA,
  CampoB,
};
</script>

<template>
  <div>
    <label>
      A
      <input type="radio" v-model="currentComponent" value="CampoA" />
    </label>
    <label>
      B
      <input type="radio" v-model="currentComponent" value="CampoB" />
    </label>

    <KeepAlive>
      <Suspense>
        <component :is="taps[currentComponent]" />
      </Suspense>
    </KeepAlive>
  </div>
</template>

<style scoped></style>
