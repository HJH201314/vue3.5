<template>
  <div>ID is: {{ num }}</div>
</template>

<script setup lang="ts">
import { toRefs, watch } from 'vue';

const props = defineProps<{
  num: number;
}>();

let { num } = toRefs(props);

watch(() => props.num, (newVal) => {
  console.log(`watch num changed ${newVal}`);
});
</script>

<style lang="css">
</style>