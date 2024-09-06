<template>
  <div>ID is: {{ num }}</div>
</template>

<script setup lang="ts">
import { watch } from 'vue';

const props = defineProps<{
  num: number;
}>();

watch(() => props.num, () => {
  console.log('watch num changed 1');
});
</script>

<style lang="css">
</style>