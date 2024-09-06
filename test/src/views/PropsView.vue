<template>
  <div class="about">
    <old-props :num="number"></old-props>
    <new-props :num="number"></new-props>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import OldProps from './props/OldProps.vue';
import NewProps from './props/NewProps.vue';

const number = ref(1);

onMounted(() => {
  setInterval(() => {
    number.value++;
  }, 1000);
});

</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
